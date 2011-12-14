require 'rubygems'
require 'bundler'
begin
  Bundler.setup(:default, :development)
rescue Bundler::BundlerError => e
  $stderr.puts e.message
  $stderr.puts "Run `bundle install` to install missing gems"
  exit e.status_code
end
require 'rake'

version = File.exist?('VERSION') ? File.read('VERSION') : ""

require 'jeweler'
Jeweler::Tasks.new do |gem|
  gem.name = "resort-bjones"
  gem.version = version
  gem.homepage = "http://github.com/bjones/resort"
  gem.license = "MIT"
  gem.summary = %Q{Positionless model sorting for Rails 3.}
  gem.description = %Q{Positionless model sorting for Rails 3.}
  gem.email = "cbj@gnu.org"
  gem.authors = ["Oriol Gual", "Josep M. Bach", "Josep Jaume Rey", "Brian Jones"]
end
Jeweler::RubygemsDotOrgTasks.new

require 'rspec/core'
require 'rspec/core/rake_task'
RSpec::Core::RakeTask.new(:spec) do |spec|
end

task :default => :spec

require 'yard'
YARD::Rake::YardocTask.new(:docs) do |t|
  t.files   = ['lib/**/*.rb']
  t.options = ['-m', 'markdown', '--no-private', '-r', 'Readme.md', '--title', 'Resort documentation']
end

task :doc => :docs

desc "Generate and open class diagram (needs Graphviz installed)"
task :graph do |t|
 `bundle exec yard graph -d --full --no-private | dot -Tpng -o graph.png && open graph.png`
end


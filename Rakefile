desc "Build the rvm gem and then install it (NO sudo)."
task :gem do
    puts `gem uninstall rvm ; rm -f ./rvm*.gem; gem build rvm.gemspec ; gem install ./rvm*.gem --no-ri -l`
end

namespace :gem do
  desc "Build the rvm gem."
  task :build do
    puts `gem build gemspec.rb`
  end

  desc "Install the rvm gem (NO sudo)."
  task :install do 
    %x{gem install rvm*.gem --no-rdoc --no-ri -l}
  end
end

begin
  require "jeweler"
  Jeweler::Tasks.new do |gemspec|
    gemspec.name            = "rvm"
    gemspec.summary         = "Ruby Version Manager (rvm)"
    gemspec.require_paths   = ["lib"]
    gemspec.date            = Time.now.strftime("%Y-%m-%d")
    gemspec.description     = "Manages Ruby interpreter installations and switching between them."
    gemspec.platform        = Gem::Platform::RUBY
    gemspec.files           = ["INSTALL", "README", "rvm.gemspec", "bash/*", Dir::glob("lib/**/**")].flatten
    gemspec.executables     = Dir::glob("bin/*").map{ |script| File::basename script }
    gemspec.require_path    = "lib"
    gemspec.has_rdoc        = File::exist?("doc")
    gemspec.rdoc_options    = ["--inline-source", "--charset=UTF-8"]
    gemspec.authors         = ["Wayne E. Seguin"]
    gemspec.email           = "wayneeseguin@gmail.com"
    gemspec.homepage        = "http://github.com/wayneeseguin/rvm"
    gemspec.extensions      << "extconf.rb" if File::exists?("extconf.rb")
    gemspec.rubyforge_project = "dynamicreports"
  end
rescue LoadError
  puts "Jeweler not available. Install it with: sudo gem install technicalpickles-jeweler -s http://gems.github.com"
end

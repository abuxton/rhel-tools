#
load 'rake/helper.rb'

desc "Run the test suite."
task :test do
  $:.unshift File.expand_path("../test", __FILE__)

    Dir["test/**/*_test.rb"].each do |f|
        load f
    end
end

desc "Set up the VM"
task :up do
  vm = VM.new
  vm.cli('up')
end

desc "Shutdown the VM"
task :graceful_down do
  vm = VM.new
  vm.sudo('halt')
end



desc "default"
task :default do
  system "rake --tasks"
end

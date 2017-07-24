#load 'rake/helper.rb'

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

desc "Start sinatra app"
task :start_sinatra do
  vm = VM.new
  status = vm.execute('rackup -D')
  raise "It didn't start" if status > 0
end

desc "Run tests at the sinatra app"
task :tests do
  vm = VM.new
  vm.execute('rake features')
end

desc "default"
task :default do
  rake -t
end

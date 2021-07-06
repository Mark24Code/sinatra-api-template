require "rake/testtask"

# TODO 优化任务


Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.test_files = FileList["test/**/*_test.rb"]
end


task :run do
  require 'socket'
  my_address = Socket.ip_address_list.detect{|intf| intf.ipv4_private?}  

  puts "server run #{my_address.ip_address}:5000"
  system("rackup -o 0.0.0.0 -p 5000")
end


task default: %w[run]
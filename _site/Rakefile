task :default => [:help]

desc "Create a new translation page, provide a page number arg"
task :page, :number  do |t, args|
  path = File.join(File.dirname(__FILE__), %w/_posts/)
  date = Time.now.to_s.split(/\s+/).first
  slug = '-de-umbris-idearum-'
  page = args[:number]
  file = "#{date}#{slug}#{page}.markdown"
  file_fullpath = File.join(path, file)

  raise "A page number must be provided" unless page

  puts file_fullpath
  File.open(file_fullpath, "w") do |f|
    f.write template
  end

end

desc "A help function"
task :help do
  puts <<-EOF
  You probably want this guy:

  `noglob rake page[##]` :: Create a new page
  EOF
end

desc "Start the server"
task :server do
  `jekyll serve -w --base '/' -P 3223`
end


def template
  return  <<-EOF
---
title: "TITLE"
layout: default
---

# Translation

----
----

# Dissection
  EOF
end

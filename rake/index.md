---
layout: default
---
# Rake

## Rules

```ruby
# Single rule
file inputfile => outputfile do
  build_instructions
end

# Task
task :taskname => %W[ dependency1 dependency2 dependency3 ]

# Default task, gets called using "rake"
task :default => :defaulttaskname

# Rule
rule ".output" => ".input" do |t|
  # Convert t.source to t.name
end

rule ".output" => ->(f) { derive_input_from_output f } do |t|
  # Convert t.source to t.name
end
```

## File Lists

```ruby
# FileList
filelist = Rake::FileList.new("*.abc", "**/*.xyz") do |f|
    f.exclude("*~")
    f.exclude(/regex/)
    f.exclude do |filename|
        # some logic
    end
end

# Replace extensions
filelist.ext('.newextension')
```

## Extra

* [Rake Basics](http://devblog.avdi.org/2014/04/21/rake-part-1-basics/)
* [Rake File Lists](http://devblog.avdi.org/2014/04/22/rake-part-2-file-lists/)
* [Rake Rules](http://devblog.avdi.org/2014/04/23/rake-part-3-rules/)
* [Rake Pathmap](http://devblog.avdi.org/2014/04/24/rake-part-4-pathmap/)
* [File Operations](http://devblog.avdi.org/2014/04/25/rake-part-5-file-operations/)
* [Clean and Clobber](http://devblog.avdi.org/2014/04/28/rake-part-6-clean-and-clobber/)
* [MultiTask](http://devblog.avdi.org/2014/04/29/rake-part-7-multitask/)
task :default => [:build_and_deploy]

task :build_and_deploy do
  system("git checkout master")

  if system("jekyll build")
    system("git add .")
    system("git commit -m 'Update'")
    system("git push")
    system("git checkout gh-pages")
    system("cp -rv _site/* .")
    system("git add .")
    system("git commit -m 'Update'")
    system("git push")
    system("git checkout master")

    puts "Done :)"
  end
end

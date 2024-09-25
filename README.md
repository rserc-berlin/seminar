
```bash
# Install ruby 3.2.5
pacman -S ruby

export PATH="/home/tim/.local/share/gem/ruby/3.2.0/bin:${PATH}"  # or add to your .zshrc or .bashrc

# Install missing dependency
gem install bundler

# Set local path
bundle config set --local path ~/.local/share/gem/ruby/3.2.0/gems/

cd seminars
bundle exec jekyll serve
```

Check out 
* https://github.com/mmistakes/minimal-mistakes
* https://github.com/Sparrow0hawk/rse-calendar
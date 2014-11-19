require 'html/proofer'

task :test do
  sh 'bundle exec jekyll build --destination _site_test/open-source-program/'

  begin
    HTML::Proofer.new('./_site_test',
      href_ignore: ['#top']
    ).run
  ensure
    FileUtils.rm_rf('_site_test')
  end
end

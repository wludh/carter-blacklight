To install
If running into errors, you might have to:
Update to sierra
Install and/or update xcode
Install command line tools
install postgres

To clone
$ git clone repo_name
$ cd repo_name
$ rvm install 2.4.0
$ rvm gemset create carter-blacklight
$ rvm gemset use carter-blacklight
$ bundle install
$ bundle exec solr_wrapper
^^ takes a while
You should be able to navigate to Solr at http://localhost:8983/solr/#/blacklight-core/query
$ rake solr:marc:index_test_data
$ rails server

To create from scratch
$ rvm install 2.4.0
$ rvm gemset create carter-blacklight
$ rvm gemset use carter-blacklight
$ gem install solr_wrapper 
$ rails new carter_blacklight -m https://raw.github.com/projectblacklight/blacklight/master/template.demo.rb
$ cd carter_blacklight
$ bundle exec solr_wrapper
^^ takes a while
You should be able to navigate to Solr at http://localhost:8983/solr/#/blacklight-core/query

$ rake solr:marc:index_test_data
$ rails server

known issues: 

nokogiri fails to install
need to install command line developer tools first:
$ xcode-select --install
and agree to popup

If that happens when running the quickstart install, you will need to rerun
$ rails generate blacklight:install --devise --marc --solr_version=latest
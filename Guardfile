require 'asciidoctor'
require 'erb'
require 'fileutils'
require 'asciidoctor-diagram'

FileUtils.mkdir_p('public')
FileUtils.cp_r('images','public')
FileUtils.cp_r('tocbot-3.0.2','public')
FileUtils.cp_r('stylesheets','public')

guard 'shell' do
  watch(/^.*\.adoc$/) {|m|
  	if m[0] != "index.adoc"
  	Asciidoctor.render_file(m[0], :to_dir => "public", :safe => Asciidoctor::SafeMode::UNSAFE, :attributes=> {'sectnums'=>'','stylesheet'=>'main.css','stylesdir'=>'stylesheets/','icons' =>'font','idprefix' => '', 'idseparator' => '-', 'copycss' => '', 'source-highlighter' => 'rouge', 'sectanchors' => '', 'doctype' => 'book', 'eruby'=>'erubis', 'toc' => 'left', 'toclevels' => '2', 'revnumber' => '1.0', 'require'=>'asciidoctor-diagram'})
  	end
    Asciidoctor.render_file("index.adoc", :to_dir => "public", :safe => Asciidoctor::SafeMode::UNSAFE, :attributes=> {'sectnums'=>'','stylesheet'=>'main.css','stylesdir'=>'stylesheets/','icons' =>'font','idprefix' => '', 'idseparator' => '-', 'copycss' => '', 'source-highlighter' => 'rouge', 'sectanchors' => '', 'doctype' => 'book', 'eruby'=>'erubis','toc' => 'left', 'toclevels' => '1', 'revnumber' => '1.0', 'require'=>'asciidoctor-diagram'})
  }
end

guard 'livereload' do
  watch(%r{public/.+\.(css|js|html)$})
end




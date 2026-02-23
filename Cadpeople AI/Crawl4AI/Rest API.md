
/crawl
{
  "urls": ["https://renewablesnow.com/news/hassan-allam-unit-contracted-to-build-200-mw-solar-project-in-egypt-1289927?utm_source=rss&utm_medium=feed&utm_campaign=rss-source/"],
  "crawler_config" : {
    "type": "CrawlerRunConfig",
    "params" : {
  "css_selector" : ".info-article",  
  "delay_before_return_html" :3
}}}

Starting the docker container on Ubuntu
docker run -d -p 11235:11235 --name crawl4ai --shm-size=1g unclecode/crawl4ai:latest


# sync-mongo-elastic
- mongo-url = “your-mongo-db-connection-string”
- elasticsearch-urls = [“your-elastic-search-url”]
- replay: When replay is true, monstache replays all events from the beginning of the MongoDB oplog and syncs them to Elasticsearch.
- resume: When resume is true, monstache writes the timestamp of MongoDB operations it has successfully synced to Elasticsearch to the collection monstache.monstache. It also reads that timestamp from that collection when it starts in order to replay events which it might have missed because monstache was stopped
- resume-name: monstache uses the value of resume-name as an id when storing and retrieving timestamps to and from the MongoDB collection monstache.monstache. The default value for this option is the string default.
- namespace-regex:When namespace-regex is given this regex is tested against the namespace, database.collection, of any insert, update, delete in MongoDB
- direct-read-namespaces:This option allows you to directly copy collections from MongoDB to Elasticsearch. You need this option if you want index all of your data from - mongodb to elasticsearch
- mapping: used to overwrite default index and type.. See the section Index Mapping for more information.

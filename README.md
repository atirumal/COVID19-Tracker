# COVID-19 Tracker

This full stack application provides real-time global statistics for COVID-19, sourcing data from Johns Hopkins University Center for Systems Science and Engineering (JHU CSSE). It runs React.js in front-end, Node.js in the back-end, and stores the data parsed from JHU CSSE in a MongoDB database.

To ensure efficient data processing, I implemented a conversion process for the data provided by JHU CSSE, originally in CSV format, into JSON format. I utilized the csv-parser npm module, which can parse ~90,000 rows per second. Once the data is parsed, I store it in a MongoDB database, reducing the need for repetitive parsing operations. To keep the data constantly up-to-date, I implemented a synchronization mechanism using the node-cron npm module. This scheduler triggers data updates daily at 23:59 (UTC), ensuring that the server remains synchronized with JHU CSSE's latest data without manual intervention.

Finally, I used the Mapbox API to populate the coordinates on the map using the GeoJSON format.

![covid19](https://github.com/atirumal/COVID19-Tracker/assets/78452887/288e2422-8477-4ef5-8d23-b8850a87145c)

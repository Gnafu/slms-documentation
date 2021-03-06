.. module:: geoserver.shp_postgis
   :synopsis: Learn how to loading a Shapefile into Postgis.

.. _geoserver.shp_postgis:

Loading a Shapefile into PostGIS
--------------------------------

This task shows how to load a ShapeFile into PostGIS database:

#. Open the terminal window and enter the following command and press enter to creating a new database named 'shape'::

     createdb -T postgis_template shape

#. Move to the GeoServer data directory, so that the Mainrd.shp file is in the current directory::
    
     cd /home/unredd/Desktop/workshop/data/user_data
     ls Mainrd.*

#. Enter the following command and press enter to load the ShapeFile into 'shape' database::

     shp2pgsql -I Mainrd.shp public.main_roads | psql -d shape

   The ShapeFile will be loaded within the 'main_roads' table of the 'shape' database. The following screenshot shows some of the table contents in ``pgAdmin III``

   .. figure:: img/shp_postgis1.png

      A PostGIS table by ShapeFile

In the :ref:`next <geoserver.postgis_lay>` section we will see how to add a PostGIS layer into GeoServer.

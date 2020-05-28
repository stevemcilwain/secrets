# Manually Make a JAR File

java -source 1.8 -target 1.8 <name>.java
mkdir META-INF; 
echo "Main-Class: <classname>" > META-INF/MANIFEST.MF
jar cmvf META-INF/MANIFEST.MF <name>.jar <name>.class
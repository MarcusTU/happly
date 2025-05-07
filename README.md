<p align="center">
<img src="https://github.com/nmwsharp/happly/blob/master/happly_logo.jpg" width="200"> 
</p>
<p align="center">A header-only C++ reader/writer for the PLY file format. Parse .ply happily! <p align="center">

### Fork log by MarcusTU

[Initial copy of nmwsharp/happly]

[Changes from 07.05.2025 by MarcusTU]

[Added]
`bool Element::hasListPropertyType`
`(const std::string& target)`
[Reason]
There was no analogon to hasPropertyType for list properties

[Added]
`std::string PLYData::getPropertyTypeName`
`(const std::string & propertyName)`
[Reason]
There was no possibility to get the property type name from the outside

[Added]
`bool Element::isListProperty`
`(const std::string & propertyName)`
[Reason]
There was no possibility to check if a property is a list property from the outside

[Added]
`std::vector<std::array<double, 3>> PLYData::getVertexNormals`
`(const std::string& vertexElementName = "vertex")`
[Reason]
There is a wrapper for positions (getVertexPositions) but the one for normals was missing

[Added]
`void PLYData::addElementNormals`
`(std::string const& elementName, std::vector<std::array<PositionT, 3>>& elementNormals)`
[Reason]
There is a wrapper for positions (addVertexPositions) but the one for normals was missing

[Added]
`void PLYData::addElementProperty`
`(std::vector<T> const & data, std::string const & elementName, std::string const & propertyName)`
[Reason]
There was no wrapper for adding data to element properties in a smooth way

[Added]
`void PLYData::addElementListProperty`
`(std::vector<std::vector<T>> const & data, std::string const & elementName, std::string const & listPropertyName)`
[Reason]
There was no wrapper for adding data to element list properties in a smooth way

[Changed]
`void PLYData::addElementColors`
`(std::string const& elementName, std::vector<std::array<double, 3>>& colors)`
[InsteadOf]
`void PLYData::addVertexColors`
`(std::vector<std::array<double, 3>>& colors)`
[Reason]
More general version of the same function that can set colors to any element and not only to vertices

[Changed]
`void PLYData::addElementColors`
`(std::string const& elementName, std::vector<std::array<unsigned char, 3>>& colors)`
[InsteadOf]
`void PLYData::addVertexColors`
`(std::vector<std::array<unsigned char, 3>>& colors)`
[Reason]
More general version of the same function that can set colors to any element and not only to vertices

[Changed]
`void PLYData::addVertexPositions`
`(std::vector<std::array<PositionT, 3>>& vertexPositions)`
[InsteadOf]
`void PLYData::addVertexPositions`
`(std::vector<std::array<double, 3>>& vertexPositions)`
[Reason]
This allows for float and double positions instead of only double ones

[Fixed C4702]
`S* addressIfSame`
`(T&, char)`
# tongcli

####

Generate class from schema defintion 


## inferring from sample 
https://github.com/RicoSuter/NJsonSchema/wiki/SampleJsonSchemaGenerator


###
https://github.com/RicoSuter/NJsonSchema

#####
class Program
{
    static void Main(string[] args)
    {
        var location = Assembly.GetExecutingAssembly().Location;
        var path = Path.GetFullPath(Path.Combine(location, @"..\..\..\Schemas"));
        var schemaJson = File.ReadAllText($"{path}Test.json");
        var schema = JsonSchema4.FromJsonAsync(schemaJson).Result;
        var generator = new CSharpGenerator(schema);
        var generatedFile = generator.GenerateFile();
    }
}

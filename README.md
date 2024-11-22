# AddingClassvs.UnderSolution

using GeneratedClasses;
using System;
using System.IO;

class Program
{
    static void Main(string[] args)
    {
        // Proje dizinini bul
        string projectPath = Directory.GetCurrentDirectory(); // Çalışma dizini
        string folderName = "C:\\Users\\emre.sen\\Desktop\\deneme\\deneme\\"; // Oluşturulacak klasör adı
        string className = "emredeneme"; // Oluşturulacak sınıf adı

        // Klasör oluştur
        string folderPath = Path.Combine(projectPath, folderName);
        if (!Directory.Exists(folderPath))
        {
            Directory.CreateDirectory(folderPath);
            Console.WriteLine($"Klasör oluşturuldu: {folderPath}");
        }

        // Class dosyası oluştur
        string classFilePath = Path.Combine(folderPath, $"{className}.cs");
        if (!File.Exists(classFilePath))
        {
            // Sınıf içeriği
            string classContent = $@"
using System;

namespace GeneratedClasses
{{
    public class {className}
    {{
        public string? Property1 {{ get; set; }}
        public int? Property2 {{ get; set; }}

        public void Method1()
        {{
            Console.WriteLine(""Bu bir dinamik sınıftır."");
        }}
    }}
}}";

            // Dosyaya yaz
            File.WriteAllText(classFilePath, classContent);
            Console.WriteLine($"Sınıf dosyası oluşturuldu: {classFilePath}");
        }
        else
        {
            Console.WriteLine($"Dosya zaten var: {classFilePath}");
        }

        emredeneme emre = new emredeneme();
        emre.Method1();
    }

  
}

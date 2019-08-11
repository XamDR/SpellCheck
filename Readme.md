# SpellCheck
Managed wrapper for the Microsoft Spell Checking API available in Windows 8 and Windows Server 2012 and later.
```
static void Main(string[] args)
{
    Console.Write("Write a misspelled word: ");
    var word = Console.ReadLine();
    Console.WriteLine("\nSuggestions:\n");
    ShowSuggestions(word);
    Console.ReadKey(true);
}

private static void ShowSuggestions(string word)
{
    using (var spellChecker = new SpellChecker())
    {
        foreach (var suggestion in spellChecker.Suggestions(word))
        {
            Console.WriteLine(suggestion);
        }
    }
}
```

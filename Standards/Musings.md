- Could JSON Schema (to defined required fields of a standard) or C# (or some structured language with interfaces, inheritance and implementations) be used as a clever way of defining a standard? Could just try it optinally as an experiment...
    - DovetailDescriptionLanguage would be an interface.
    - Any abstract implementations would be interfaces that inherit or an abstract class.
    - Any concrete implementations would be the bottom layer that fully implements all inherited interfaces/abstract classes.
    
Ex of C# def:

```
// needs hella work, syntax isn't even correct
public interface ICodifiedStandard
{
    public string Id; // Must be unique globally
    public string PlainName;
    public string Description; // High level blurb
    public string[] Features; // A list of features provided by this standard.
    public string Purpose; // More in depth description of why this standard was defined and what problems it solves.
    public datetime2 DateOfInception; // Duh

}

public abstract class IDovetailDescriptionLanguage : ICodifiedStandard
{
    public string Id { get { return "DovetailDescriptionLanguage"; } };
    public string PlainName { return "Dovetail Description Language"; } } ;
    public string Description {get { return "To provide a framework for describing the features of a Dovetail ss a standard system";}
    public string[] Features {get;set;}
    public string Purpose {get { return "Even more simply, to allow a dovetail to quickly be described as the expression of three terms. Ex A 457 dovetail.";}
    public datetime2 DateOfInception {get { return "2026-03-14";} } }
    
    public abstract decimal DovetailBaseWidth_Half;
    public abstract decimal DovetailThickness;
    public abstract decimal DovetailTopWidth_Half;
}

public interface DDL457 : IDovetailDescriptionLanguage
{
    public string Id { get { return "DDL457"; } };
    public string PlainName { return "457 Dovetail"; } } ;
    public string Description {get { return "To provide a framework for describing the features of a Dovetail ss a standard system";}
    public string[] Features {get;set;}
    public string Purpose {get { return "Even more simply, to allow a dovetail to quickly be described as the expression of three terms. Ex A 457 dovetail.";}
    public datetime2 DateOfInception {get { return "2026-03-14";} } }
    
    
    public const decimal DovetailBaseWidth_Half = 4;
    public const decimal DovetailThickness = 5;
    public const decimal DovetailTopWidth_Half = 7;
}
```
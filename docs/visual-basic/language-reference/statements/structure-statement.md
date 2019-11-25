---
title: Structure 문
ms.date: 05/12/2018
f1_keywords:
- vb.Structure
- Structure
helpviewer_keywords:
- user-defined types [Visual Basic], Structure statement
- compound data types [Visual Basic]
- Structure keyword [Visual Basic]
- Structure statement [Visual Basic]
- UDT (user-defined types)
- types [Visual Basic], user-defined
ms.assetid: 9bd1deea-2a89-4cdc-812c-6dcbb947c391
ms.openlocfilehash: 120f836b9d49c00e9c53af0d1fc832e22c8cbbb8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346453"
---
# <a name="structure-statement"></a>Structure 문

Declares the name of a structure and introduces the definition of the variables, properties, events, and procedures that the structure comprises.

## <a name="syntax"></a>구문

```vb
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Partial ] _
Structure name [ ( Of typelist ) ]
    [ Implements interfacenames ]
    [ datamemberdeclarations ]
    [ methodmemberdeclarations ]
End Structure
```

## <a name="parts"></a>요소

|용어|정의|
|---|---|
|`attributelist`|(선택 사항) See [Attribute List](attribute-list.md).|
|`accessmodifier`|(선택 사항) 다음 중 하나일 수 있습니다.<br /><br /> -   [Public](../modifiers/public.md)<br />-   [Protected](../modifiers/protected.md)<br />-   [Friend](../modifiers/friend.md)<br />-   [Private](../modifiers/private.md)<br />- [Protected Friend](../modifiers/protected-friend.md)<br/>- [Private Protected](../modifiers/private-protected.md) <br /><br /> [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.|
|`Shadows`|(선택 사항) See [Shadows](../modifiers/shadows.md).|
|`Partial`|(선택 사항) Indicates a partial definition of the structure. See [Partial](../modifiers/partial.md).|
|`name`|필수 요소. Name of this structure. [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.|
|`Of`|(선택 사항) Specifies that this is a generic structure.|
|`typelist`|Required if you use the [Of](of-clause.md) keyword. List of type parameters for this structure. See [Type List](type-list.md).|
|`Implements`|(선택 사항) Indicates that this structure implements the members of one or more interfaces. See [Implements Statement](implements-statement.md).|
|`interfacenames`|Required if you use the `Implements` statement. The names of the interfaces this structure implements.|
|`datamemberdeclarations`|필수 요소. Zero or more `Const`, `Dim`, `Enum`, or `Event` statements declaring *data members* of the structure.|
|`methodmemberdeclarations`|(선택 사항) Zero or more declarations of `Function`, `Operator`, `Property`, or `Sub` procedures, which serve as *method members* of the structure.|
|`End Structure`|필수 요소. Terminates the `Structure` definition.|

## <a name="remarks"></a>주의

The `Structure` statement defines a composite value type that you can customize. A *structure* is a generalization of the user-defined type (UDT) of previous versions of Visual Basic. For more information, see [Structures](../../programming-guide/language-features/data-types/structures.md).

Structures support many of the same features as classes. For example, structures can have properties and procedures, they can implement interfaces, and they can have parameterized constructors. However, there are significant differences between structures and classes in areas such as inheritance, declarations, and usage. Also, classes are reference types and structures are value types. For more information, see [Structures and Classes](../../programming-guide/language-features/data-types/structures-and-classes.md).

You can use `Structure` only at namespace or module level. This means the *declaration context* for a structure must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure or block. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](declaration-contexts-and-default-access-levels.md)을 참조하세요.

Structures default to [Friend](../modifiers/friend.md) access. You can adjust their access levels with the access modifiers. For more information, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

## <a name="rules"></a>규칙

- **Nesting.** You can define one structure within another. The outer structure is called the *containing structure*, and the inner structure is called a *nested structure*. However, you cannot access a nested structure's members through the containing structure. Instead, you must declare a variable of the nested structure's data type.

- **Member Declaration.** You must declare every member of a structure. A structure member cannot be [Protected](../modifiers/protected.md) or `Protected Friend` because nothing can inherit from a structure. The structure itself, however, can be `Protected` or `Protected Friend`.
  
     구조체에는 0개 이상의 비공유 변수 또는 비공유, 비사용자 정의 이벤트를 선언할 수 있습니다. You cannot have only constants, properties, and procedures, even if some of them are nonshared.

- **Initialization.** You cannot initialize the value of any nonshared data member of a structure as part of its declaration. You must either initialize such a data member by means of a parameterized constructor on the structure, or assign a value to the member after you have created an instance of the structure.

- **상속.** A structure cannot inherit from any type other than <xref:System.ValueType>, from which all structures inherit. In particular, one structure cannot inherit from another.

     You cannot use the [Inherits Statement](inherits-statement.md) in a structure definition, even to specify <xref:System.ValueType>.

- **Implementation.** If the structure uses the [Implements Statement](implements-statement.md), you must implement every member defined by every interface you specify in `interfacenames`.

- **Default Property.** A structure can specify at most one property as its *default property*, using the [Default](../modifiers/default.md) modifier. For more information, see [Default](../modifiers/default.md).

## <a name="behavior"></a>동작

- **Access Level.** Within a structure, you can declare each member with its own access level. All structure members default to [Public](../modifiers/public.md) access. Note that if the structure itself has a more restricted access level, this automatically restricts access to its members, even if you adjust their access levels with the access modifiers.

- **Scope.** A structure is in scope throughout its containing namespace, class, structure, or module.

     The scope of every structure member is the entire structure.

- **Lifetime.** A structure does not itself have a lifetime. Rather, each instance of that structure has a lifetime independent of all other instances.

     The lifetime of an instance begins when it is created by a [New Operator](../operators/new-operator.md) clause. It ends when the lifetime of the variable that holds it ends.

     You cannot extend the lifetime of a structure instance. An approximation to static structure functionality is provided by a module. For more information, see [Module Statement](module-statement.md).

     Structure members have lifetimes depending on how and where they are declared. For more information, see "Lifetime" in [Class Statement](class-statement.md).

- **Qualification.** Code outside a structure must qualify a member's name with the name of that structure.

     If code inside a nested structure makes an unqualified reference to a programming element, Visual Basic searches for the element first in the nested structure, then in its containing structure, and so on out to the outermost containing element. 자세한 내용은 [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)을 참조하세요.

- **Memory Consumption.** As with all composite data types, you cannot safely calculate the total memory consumption of a structure by adding together the nominal storage allocations of its members. Furthermore, you cannot safely assume that the order of storage in memory is the same as your order of declaration. If you need to control the storage layout of a structure, you can apply the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute to the `Structure` statement.

## <a name="example"></a>예제

The following example uses the `Structure` statement to define a set of related data for an employee. It shows the use of `Public`, `Friend`, and `Private` members to reflect the sensitivity of the data items. It also shows procedure, property, and event members.

[!code-vb[VbVbalrStatements#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#57)]

For more information on how to use `Structure`s, see [Structure Variable](../../programming-guide/language-features/data-types/structure-variables.md).

## <a name="see-also"></a>참조

- [Class 문](class-statement.md)
- [Interface 문](interface-statement.md)
- [Module 문](module-statement.md)
- [Dim 문](dim-statement.md)
- [Const 문](const-statement.md)
- [Enum 문](enum-statement.md)
- [Event 문](event-statement.md)
- [Operator 문](operator-statement.md)
- [Property 문](property-statement.md)
- [구조체와 클래스](../../programming-guide/language-features/data-types/structures-and-classes.md)

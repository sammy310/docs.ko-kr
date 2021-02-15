---
description: '자세한 정보: 방법: 리플렉션을 사용 하 여 어셈블리의 메타 데이터 쿼리 (LINQ) (Visual Basic)'
title: '방법: 리플렉션을 사용하여 어셈블리의 메타데이터 쿼리(LINQ)'
ms.date: 07/20/2015
ms.assetid: 53caa336-ab83-4181-b0f6-5c87c5f9e4ee
ms.openlocfilehash: 2e0f242112ddbac3d88d7d0173550978f8784cef
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100477543"
---
# <a name="how-to-query-an-assemblys-metadata-with-reflection-linq-visual-basic"></a>방법: 리플렉션을 사용 하 여 어셈블리의 메타 데이터 쿼리 (LINQ) (Visual Basic)

다음 예제에서는 리플렉션과 함께 LINQ를 사용하여 지정된 검색 조건과 일치하는 메서드에 대한 특정 메타데이터를 검색하는 방법을 보여 줍니다. 이 경우 쿼리는 배열과 같은 열거 가능한 형식을 반환하는 모든 메서드의 이름을 어셈블리에서 검색합니다.  
  
## <a name="example"></a>예제  
  
```vb
Imports System.Linq
Imports System.Reflection  

Module Module1  
    Sub Main()  
        Dim asmbly As Assembly =
            Assembly.Load("System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken= b77a5c561934e089")  
  
        Dim pubTypesQuery = From type In asmbly.GetTypes()
                            Where type.IsPublic
                            From method In type.GetMethods()
                            Where method.ReturnType.IsArray = True
                            Let name = method.ToString()
                            Let typeName = type.ToString()
                            Group name By typeName Into methodNames = Group  
  
        Console.WriteLine("Getting ready to iterate")  
        For Each item In pubTypesQuery  
            Console.WriteLine(item.methodNames)  
  
            For Each type In item.methodNames  
                Console.WriteLine(" " & type)  
            Next  
        Next  
        Console.WriteLine("Press any key to exit... ")  
        Console.ReadKey()  
    End Sub  
End Module  
```  
  
이 예제에서는 <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> 메서드를 사용하여 지정된 어셈블리의 형식 배열을 반환합니다. [Where 절](../../../language-reference/queries/where-clause.md) 필터는 public 형식만 반환 되도록 적용 됩니다. 각 public 형식에 대해 <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> 호출에서 반환된 <xref:System.Reflection.MethodInfo> 배열을 사용하여 하위 쿼리가 생성됩니다. 이러한 결과는 해당 반환 형식이 배열이거나 <xref:System.Collections.Generic.IEnumerable%601>을 구현하는 형식인 메서드만 반환하도록 필터링됩니다. 마지막으로, 이러한 결과는 형식 이름을 키로 사용하여 그룹화됩니다.  
  
## <a name="see-also"></a>참조

- [LINQ to Objects(Visual Basic)](linq-to-objects.md)

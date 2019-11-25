---
title: GetType Operator
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 4e59bcfaa24c9545ed75c6b5c1d29cad398ac2de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349546"
---
# <a name="gettype-operator-visual-basic"></a>GetType 연산자(Visual Basic)
Returns a <xref:System.Type> object for the specified type. The <xref:System.Type> object provides information about the type such as its properties, methods, and events.  
  
## <a name="syntax"></a>구문  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---|---|  
|`typename`|The name of the type for which you desire information.|  
  
## <a name="remarks"></a>주의  
 The `GetType` operator returns the <xref:System.Type> object for the specified `typename`. You can pass the name of any defined type in `typename`. 여기에는 다음과 같은 사항이 포함됩니다.  
  
- Any Visual Basic data type, such as `Boolean` or `Date`.  
  
- Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.  
  
- Any class, structure, module, or interface defined by your application.  
  
- Any array defined by your application.  
  
- Any delegate defined by your application.  
  
- Any enumeration defined by Visual Basic, the .NET Framework, or your application.  
  
 If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.  
  
 The `GetType` operator can be useful in the following circumstances:  
  
- You must access the metadata for a type at run time. The <xref:System.Type> object supplies metadata such as type members and deployment information. You need this, for example, to reflect over an assembly. 자세한 내용은 <xref:System.Reflection?displayProperty=nameWithType>를 참조하세요.  
  
- You want to compare two object references to see if they refer to instances of the same type. If they do, `GetType` returns references to the same <xref:System.Type> object.  
  
## <a name="example"></a>예제  
 The following examples show the `GetType` operator in use.  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a>참조

- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [연산자 및 식](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)

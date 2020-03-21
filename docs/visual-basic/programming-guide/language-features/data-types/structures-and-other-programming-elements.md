---
title: 구조체 및 기타 프로그래밍 요소
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], arrays
- procedures [Visual Basic], structures as arguments to
- objects [Visual Basic], structure elements
- arrays [Visual Basic], structure elements
- nested structures [Visual Basic]
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
ms.openlocfilehash: 73d3f999e95c484dff3f5409f2cdb9032b64fe38
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266861"
---
# <a name="structures-and-other-programming-elements-visual-basic"></a>구조체 및 기타 프로그래밍 요소(Visual Basic)
구조체는 배열, 개체 및 프로시저와 함께 사용할 수 있을 뿐만 아니라 서로 사용할 수 있습니다. 상호 작용은 이러한 요소가 개별적으로 사용하는 것과 동일한 구문을 사용합니다.  
  
> [!NOTE]
> 구조체 선언에서 구조 요소를 초기화할 수 없습니다. 구조체 유형으로 선언된 변수의 요소에만 값을 할당할 수 있습니다.  
  
## <a name="structures-and-arrays"></a>구조 및 배열  
 구조체는 배열을 하나 이상의 요소로 포함할 수 있습니다. 다음은 이에 대한 예입니다.  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure
```  
  
 개체의 속성에 액세스하는 것과 동일한 방식으로 구조체 내에서 배열의 값에 액세스합니다. 다음은 이에 대한 예입니다.  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 구조의 배열을 선언할 수도 있습니다. 다음은 이에 대한 예입니다.  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 동일한 규칙을 따라 이 데이터 아키텍처의 구성 요소에 액세스합니다. 다음은 이에 대한 예입니다.  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a>구조 및 객체  
 구조체는 객체를 하나 이상의 요소로 포함할 수 있습니다. 다음은 이에 대한 예입니다.  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 이러한 선언에서 특정 개체 클래스를 사용 `Object`해야 합니다.  
  
## <a name="structures-and-procedures"></a>구조 및 절차  
 구조를 프로시저 인수로 전달할 수 있습니다. 다음은 이에 대한 예입니다.  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 앞의 예제에서는 구조를 *참조로*전달하므로 프로시저가 해당 요소를 수정하여 변경 내용이 호출 코드에서 적용됩니다. 이러한 수정으로부터 구조를 보호하려면 값으로 전달합니다.  
  
 프로시저에서 구조를 반환할 `Function` 수도 있습니다. 다음은 이에 대한 예입니다.  
  
```vb  
Dim allSystems(100) As systemInfo  
Function findByDate(ByVal searchDate As Date) As systemInfo  
    Dim i As Integer  
    For i = 1 To 100  
        If allSystems(i).purchaseDate = searchDate Then Return allSystems(i)  
    Next i  
   ' Process error: system with desired purchase date not found.  
End Function  
```  
  
## <a name="structures-within-structures"></a>구조 내의 구조  
 구조체는 다른 구조를 포함할 수 있습니다. 다음은 이에 대한 예입니다.  
  
```vb  
Public Structure driveInfo  
    Public type As String  
    Public size As Long  
End Structure  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As driveInfo  
    Public purchaseDate As Date  
End Structure  
```  
  
```vb  
Dim allSystems(100) As systemInfo  
ReDim allSystems(1).diskDrives(3)  
allSystems(1).diskDrives(0).type = "Floppy"  
```  
  
 이 기술을 사용하여 다른 모듈에 정의된 구조 내에서 하나의 모듈에 정의된 구조를 캡슐화할 수도 있습니다.  
  
 구조체는 임의의 깊이에 대한 다른 구조를 포함할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- [데이터 유형](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [기본 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [복합 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [구조](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [방법: 구조체 선언](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [구조체 변수](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [구조체와 클래스](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Structure 문](../../../../visual-basic/language-reference/statements/structure-statement.md)

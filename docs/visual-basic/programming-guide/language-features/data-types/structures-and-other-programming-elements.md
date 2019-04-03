---
title: 구조체 및 기타 프로그래밍 요소(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], arrays
- procedures [Visual Basic], structures as arguments to
- objects [Visual Basic], structure elements
- arrays [Visual Basic], structure elements
- nested structures [Visual Basic]
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
ms.openlocfilehash: a943bbdec617ba6c95685df3a4fcdb36b52def22
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819111"
---
# <a name="structures-and-other-programming-elements-visual-basic"></a>구조체 및 기타 프로그래밍 요소(Visual Basic)
함께 서로 뿐만 아니라 배열, 개체 및 프로시저를 사용 하 여 구조를 사용할 수 있습니다. 이러한 요소를 개별적으로 사용 하는 대로 동일한 구문을 사용 하 여 상호 작용 합니다.  
  
> [!NOTE]
>  구조체 선언에서는 구조 요소를 초기화할 수 없습니다. 구조 형식으로 선언 된 변수는 요소에만 값을 할당할 수 있습니다.  
  
## <a name="structures-and-arrays"></a>구조체 및 배열  
 구조체의 해당 요소 중 하나 이상으로 배열을 포함할 수 있습니다. 다음은 이에 대한 예입니다.  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure   
```  
  
 개체의 속성에 액세스 하는 동일한 방식으로 구조 내에서 배열의 값 액세스할 수 있습니다. 다음은 이에 대한 예입니다.  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 구조체의 배열을 선언할 수도 있습니다. 다음은 이에 대한 예입니다.  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 이 데이터 아키텍처의 구성 요소에 액세스 하려면 동일한 규칙을 따릅니다. 다음은 이에 대한 예입니다.  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a>구조 및 개체  
 구조체의 해당 요소 중 하나 이상으로 개체를 포함할 수 있습니다. 다음은 이에 대한 예입니다.  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 이러한 선언에서 특정 개체 클래스를 사용 해야 하면 대신 `Object`합니다.  
  
## <a name="structures-and-procedures"></a>구조 및 프로시저  
 프로시저 인수로 구조체를 전달할 수 있습니다. 다음은 이에 대한 예입니다.  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 앞의 예제에서는 구조체를 전달 *참조별*, 호출 코드에서 변경 내용이 적용 되도록 해당 요소를 수정 하는 절차를 허용 하는 합니다. 이러한 수정에 대 한 구조를 보호 하려는 경우 값으로 전달 합니다.  
  
 구조를 반환할 수도 있습니다는 `Function` 프로시저입니다. 다음은 이에 대한 예입니다.  
  
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
  
## <a name="structures-within-structures"></a>구조 내에서 구조  
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
  
 또한 다른 모듈에 정의 된 구조 내에서 하나의 모듈에 정의 된 구조체를 캡슐화 하이 기법을 사용할 수 있습니다.  
  
 구조에는 다른 구조를 임의 깊이까지 포함할 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [기본 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [복합 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [구조체](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [방법: 구조 선언](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [구조체 변수](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [구조체와 클래스](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Structure 문](../../../../visual-basic/language-reference/statements/structure-statement.md)

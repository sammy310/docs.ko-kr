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
# <a name="structures-and-other-programming-elements-visual-basic"></a><span data-ttu-id="a11e5-102">구조체 및 기타 프로그래밍 요소(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a11e5-102">Structures and Other Programming Elements (Visual Basic)</span></span>
<span data-ttu-id="a11e5-103">구조체는 배열, 개체 및 프로시저와 함께 사용할 수 있을 뿐만 아니라 서로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-103">You can use structures in conjunction with arrays, objects, and procedures, as well as with each other.</span></span> <span data-ttu-id="a11e5-104">상호 작용은 이러한 요소가 개별적으로 사용하는 것과 동일한 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-104">The interactions use the same syntax as these elements use individually.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a11e5-105">구조체 선언에서 구조 요소를 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-105">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="a11e5-106">구조체 유형으로 선언된 변수의 요소에만 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-106">You can assign values only to elements of a variable that has been declared to be of a structure type.</span></span>  
  
## <a name="structures-and-arrays"></a><span data-ttu-id="a11e5-107">구조 및 배열</span><span class="sxs-lookup"><span data-stu-id="a11e5-107">Structures and Arrays</span></span>  
 <span data-ttu-id="a11e5-108">구조체는 배열을 하나 이상의 요소로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-108">A structure can contain an array as one or more of its elements.</span></span> <span data-ttu-id="a11e5-109">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-109">The following example illustrates this.</span></span>  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure
```  
  
 <span data-ttu-id="a11e5-110">개체의 속성에 액세스하는 것과 동일한 방식으로 구조체 내에서 배열의 값에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-110">You access the values of an array within a structure the same way you access a property on an object.</span></span> <span data-ttu-id="a11e5-111">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-111">The following example illustrates this.</span></span>  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 <span data-ttu-id="a11e5-112">구조의 배열을 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-112">You can also declare an array of structures.</span></span> <span data-ttu-id="a11e5-113">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-113">The following example illustrates this.</span></span>  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 <span data-ttu-id="a11e5-114">동일한 규칙을 따라 이 데이터 아키텍처의 구성 요소에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-114">You follow the same rules to access the components of this data architecture.</span></span> <span data-ttu-id="a11e5-115">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-115">The following example illustrates this.</span></span>  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a><span data-ttu-id="a11e5-116">구조 및 객체</span><span class="sxs-lookup"><span data-stu-id="a11e5-116">Structures and Objects</span></span>  
 <span data-ttu-id="a11e5-117">구조체는 객체를 하나 이상의 요소로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-117">A structure can contain an object as one or more of its elements.</span></span> <span data-ttu-id="a11e5-118">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-118">The following example illustrates this.</span></span>  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 <span data-ttu-id="a11e5-119">이러한 선언에서 특정 개체 클래스를 사용 `Object`해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-119">You should use a specific object class in such a declaration, rather than `Object`.</span></span>  
  
## <a name="structures-and-procedures"></a><span data-ttu-id="a11e5-120">구조 및 절차</span><span class="sxs-lookup"><span data-stu-id="a11e5-120">Structures and Procedures</span></span>  
 <span data-ttu-id="a11e5-121">구조를 프로시저 인수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-121">You can pass a structure as a procedure argument.</span></span> <span data-ttu-id="a11e5-122">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-122">The following example illustrates this.</span></span>  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 <span data-ttu-id="a11e5-123">앞의 예제에서는 구조를 *참조로*전달하므로 프로시저가 해당 요소를 수정하여 변경 내용이 호출 코드에서 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-123">The preceding example passes the structure *by reference*, which allows the procedure to modify its elements so that the changes take effect in the calling code.</span></span> <span data-ttu-id="a11e5-124">이러한 수정으로부터 구조를 보호하려면 값으로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-124">If you want to protect a structure against such modification, pass it by value.</span></span>  
  
 <span data-ttu-id="a11e5-125">프로시저에서 구조를 반환할 `Function` 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-125">You can also return a structure from a `Function` procedure.</span></span> <span data-ttu-id="a11e5-126">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-126">The following example illustrates this.</span></span>  
  
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
  
## <a name="structures-within-structures"></a><span data-ttu-id="a11e5-127">구조 내의 구조</span><span class="sxs-lookup"><span data-stu-id="a11e5-127">Structures Within Structures</span></span>  
 <span data-ttu-id="a11e5-128">구조체는 다른 구조를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-128">Structures can contain other structures.</span></span> <span data-ttu-id="a11e5-129">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-129">The following example illustrates this.</span></span>  
  
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
  
 <span data-ttu-id="a11e5-130">이 기술을 사용하여 다른 모듈에 정의된 구조 내에서 하나의 모듈에 정의된 구조를 캡슐화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-130">You can also use this technique to encapsulate a structure defined in one module within a structure defined in a different module.</span></span>  
  
 <span data-ttu-id="a11e5-131">구조체는 임의의 깊이에 대한 다른 구조를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-131">Structures can contain other structures to an arbitrary depth.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a11e5-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a11e5-132">See also</span></span>

- [<span data-ttu-id="a11e5-133">데이터 유형</span><span class="sxs-lookup"><span data-stu-id="a11e5-133">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="a11e5-134">기본 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a11e5-134">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="a11e5-135">복합 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a11e5-135">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="a11e5-136">값 형식과 참조 형식</span><span class="sxs-lookup"><span data-stu-id="a11e5-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="a11e5-137">구조</span><span class="sxs-lookup"><span data-stu-id="a11e5-137">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="a11e5-138">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="a11e5-138">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="a11e5-139">방법: 구조체 선언</span><span class="sxs-lookup"><span data-stu-id="a11e5-139">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="a11e5-140">구조체 변수</span><span class="sxs-lookup"><span data-stu-id="a11e5-140">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [<span data-ttu-id="a11e5-141">구조체와 클래스</span><span class="sxs-lookup"><span data-stu-id="a11e5-141">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="a11e5-142">Structure 문</span><span class="sxs-lookup"><span data-stu-id="a11e5-142">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)

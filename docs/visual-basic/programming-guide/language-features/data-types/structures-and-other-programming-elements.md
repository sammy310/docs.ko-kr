---
description: '에 대 한 자세한 정보: 구조체 및 기타 프로그래밍 요소 (Visual Basic)'
title: 구조체 및 기타 프로그래밍 요소
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], arrays
- procedures [Visual Basic], structures as arguments to
- objects [Visual Basic], structure elements
- arrays [Visual Basic], structure elements
- nested structures [Visual Basic]
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
ms.openlocfilehash: 62052389b617849566a3cd0c475a2eb5da9e61ca
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100430588"
---
# <a name="structures-and-other-programming-elements-visual-basic"></a><span data-ttu-id="8d0aa-103">구조체 및 기타 프로그래밍 요소(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d0aa-103">Structures and Other Programming Elements (Visual Basic)</span></span>

<span data-ttu-id="8d0aa-104">구조체는 물론 배열, 개체 및 프로시저와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-104">You can use structures in conjunction with arrays, objects, and procedures, as well as with each other.</span></span> <span data-ttu-id="8d0aa-105">상호 작용에서는 이러한 요소를 개별적으로 사용 하는 것과 동일한 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-105">The interactions use the same syntax as these elements use individually.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d0aa-106">구조체 선언에서 구조체 요소를 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-106">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="8d0aa-107">구조체 형식으로 선언 된 변수의 요소에만 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-107">You can assign values only to elements of a variable that has been declared to be of a structure type.</span></span>  
  
## <a name="structures-and-arrays"></a><span data-ttu-id="8d0aa-108">구조체 및 배열</span><span class="sxs-lookup"><span data-stu-id="8d0aa-108">Structures and Arrays</span></span>  

 <span data-ttu-id="8d0aa-109">구조체는 배열을 하나 이상의 요소로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-109">A structure can contain an array as one or more of its elements.</span></span> <span data-ttu-id="8d0aa-110">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-110">The following example illustrates this.</span></span>  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure
```  
  
 <span data-ttu-id="8d0aa-111">개체의 속성에 액세스 하는 것과 동일한 방식으로 구조체 내의 배열 값에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-111">You access the values of an array within a structure the same way you access a property on an object.</span></span> <span data-ttu-id="8d0aa-112">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-112">The following example illustrates this.</span></span>  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 <span data-ttu-id="8d0aa-113">구조체의 배열을 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-113">You can also declare an array of structures.</span></span> <span data-ttu-id="8d0aa-114">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-114">The following example illustrates this.</span></span>  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 <span data-ttu-id="8d0aa-115">동일한 규칙에 따라이 데이터 아키텍처의 구성 요소에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-115">You follow the same rules to access the components of this data architecture.</span></span> <span data-ttu-id="8d0aa-116">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-116">The following example illustrates this.</span></span>  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a><span data-ttu-id="8d0aa-117">구조체 및 개체</span><span class="sxs-lookup"><span data-stu-id="8d0aa-117">Structures and Objects</span></span>  

 <span data-ttu-id="8d0aa-118">구조체에는 개체를 하나 이상의 요소로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-118">A structure can contain an object as one or more of its elements.</span></span> <span data-ttu-id="8d0aa-119">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-119">The following example illustrates this.</span></span>  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 <span data-ttu-id="8d0aa-120">이 아닌 선언에서 특정 개체 클래스를 사용 해야 합니다 `Object` .</span><span class="sxs-lookup"><span data-stu-id="8d0aa-120">You should use a specific object class in such a declaration, rather than `Object`.</span></span>  
  
## <a name="structures-and-procedures"></a><span data-ttu-id="8d0aa-121">구조 및 프로시저</span><span class="sxs-lookup"><span data-stu-id="8d0aa-121">Structures and Procedures</span></span>  

 <span data-ttu-id="8d0aa-122">구조체를 프로시저 인수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-122">You can pass a structure as a procedure argument.</span></span> <span data-ttu-id="8d0aa-123">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-123">The following example illustrates this.</span></span>  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 <span data-ttu-id="8d0aa-124">앞의 예제에서는 구조체를 *참조로* 전달 합니다. 그러면 프로시저에서 해당 요소를 수정 하 여 호출 코드에 변경 내용이 적용 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-124">The preceding example passes the structure *by reference*, which allows the procedure to modify its elements so that the changes take effect in the calling code.</span></span> <span data-ttu-id="8d0aa-125">이러한 수정에 대해 구조를 보호 하려면 값으로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-125">If you want to protect a structure against such modification, pass it by value.</span></span>  
  
 <span data-ttu-id="8d0aa-126">프로시저에서 구조체를 반환할 수도 있습니다 `Function` .</span><span class="sxs-lookup"><span data-stu-id="8d0aa-126">You can also return a structure from a `Function` procedure.</span></span> <span data-ttu-id="8d0aa-127">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-127">The following example illustrates this.</span></span>  
  
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
  
## <a name="structures-within-structures"></a><span data-ttu-id="8d0aa-128">구조체 내 구조</span><span class="sxs-lookup"><span data-stu-id="8d0aa-128">Structures Within Structures</span></span>  

 <span data-ttu-id="8d0aa-129">구조체는 다른 구조체를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-129">Structures can contain other structures.</span></span> <span data-ttu-id="8d0aa-130">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-130">The following example illustrates this.</span></span>  
  
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
  
 <span data-ttu-id="8d0aa-131">이 기술을 사용 하 여 다른 모듈에 정의 된 구조 내에서 한 모듈에 정의 된 구조체를 캡슐화 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-131">You can also use this technique to encapsulate a structure defined in one module within a structure defined in a different module.</span></span>  
  
 <span data-ttu-id="8d0aa-132">구조체에는 임의의 깊이에 대 한 다른 구조가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0aa-132">Structures can contain other structures to an arbitrary depth.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d0aa-133">추가 정보</span><span class="sxs-lookup"><span data-stu-id="8d0aa-133">See also</span></span>

- [<span data-ttu-id="8d0aa-134">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8d0aa-134">Data Types</span></span>](index.md)
- [<span data-ttu-id="8d0aa-135">기본 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8d0aa-135">Elementary Data Types</span></span>](elementary-data-types.md)
- [<span data-ttu-id="8d0aa-136">복합 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8d0aa-136">Composite Data Types</span></span>](composite-data-types.md)
- [<span data-ttu-id="8d0aa-137">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="8d0aa-137">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="8d0aa-138">구조체</span><span class="sxs-lookup"><span data-stu-id="8d0aa-138">Structures</span></span>](structures.md)
- [<span data-ttu-id="8d0aa-139">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="8d0aa-139">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="8d0aa-140">방법: 구조 선언</span><span class="sxs-lookup"><span data-stu-id="8d0aa-140">How to: Declare a Structure</span></span>](how-to-declare-a-structure.md)
- [<span data-ttu-id="8d0aa-141">구조체 변수</span><span class="sxs-lookup"><span data-stu-id="8d0aa-141">Structure Variables</span></span>](structure-variables.md)
- [<span data-ttu-id="8d0aa-142">구조체와 클래스</span><span class="sxs-lookup"><span data-stu-id="8d0aa-142">Structures and Classes</span></span>](structures-and-classes.md)
- [<span data-ttu-id="8d0aa-143">Structure 문</span><span class="sxs-lookup"><span data-stu-id="8d0aa-143">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)

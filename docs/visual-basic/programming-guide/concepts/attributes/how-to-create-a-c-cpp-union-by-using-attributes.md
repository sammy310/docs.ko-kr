---
title: '방법: C-만들기C++ 특성 (Visual Basic)를 사용 하 여 공용 구조체'
ms.date: 07/20/2015
ms.assetid: 9352a7e4-c0da-4d07-aa14-55ed43736fcb
ms.openlocfilehash: 0c3ebf248f5d2f20e2fff25fb8326a294b51d153
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789092"
---
# <a name="how-to-create-a-cc-union-by-using-attributes-visual-basic"></a><span data-ttu-id="d9062-102">방법: C를 만들기 /C++ 특성 (Visual Basic)를 사용 하 여 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="d9062-102">How to: Create a C/C++ Union by Using Attributes (Visual Basic)</span></span>
<span data-ttu-id="d9062-103">특성을 사용하면 메모리에서 구조체가 레이아웃되는 방식을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9062-103">By using attributes you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="d9062-104">예를 들어 `StructLayout(LayoutKind.Explicit)` 및 `FieldOffset` 특성을 사용하여 C/C++에서 공용 구조체로 알려진 항목을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9062-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9062-105">예제</span><span class="sxs-lookup"><span data-stu-id="d9062-105">Example</span></span>  
 <span data-ttu-id="d9062-106">이 코드 세그먼트에서 `TestUnion`의 모든 필드는 메모리의 같은 위치에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d9062-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>  
  
```vb  
' Add an Imports statement for System.Runtime.InteropServices.  
  
<System.Runtime.InteropServices.StructLayout(   
      System.Runtime.InteropServices.LayoutKind.Explicit)>   
Structure TestUnion  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public i As Integer  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public d As Double  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public c As Char  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public b As Byte  
End Structure  
```  
  
## <a name="example"></a><span data-ttu-id="d9062-107">예제</span><span class="sxs-lookup"><span data-stu-id="d9062-107">Example</span></span>  
 <span data-ttu-id="d9062-108">다음은 명시적으로 설정된 다른 위치에서 필드가 시작하는 또 다른 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d9062-108">The following is another example where fields start at different explicitly set locations.</span></span>  
  
```vb  
' Add an Imports statement for System.Runtime.InteropServices.  
  
 <System.Runtime.InteropServices.StructLayout(  
      System.Runtime.InteropServices.LayoutKind.Explicit)>   
Structure TestExplicit  
     <System.Runtime.InteropServices.FieldOffset(0)>   
     Public lg As Long  
  
     <System.Runtime.InteropServices.FieldOffset(0)>   
     Public i1 As Integer  
  
     <System.Runtime.InteropServices.FieldOffset(4)>   
     Public i2 As Integer  
  
     <System.Runtime.InteropServices.FieldOffset(8)>   
     Public d As Double  
  
     <System.Runtime.InteropServices.FieldOffset(12)>   
     Public c As Char  
  
     <System.Runtime.InteropServices.FieldOffset(14)>   
     Public b As Byte  
 End Structure  
```  
  
 <span data-ttu-id="d9062-109">두 개의 정수 필드 `i1` 및 `i2`는 `lg`와 동일한 메모리 위치를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="d9062-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="d9062-110">구조체 레이아웃에 대한 이러한 종류의 제어는 플랫폼 호출을 사용할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d9062-110">This sort of control over struct layout is useful when using platform invocation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9062-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="d9062-111">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="d9062-112">Visual Basic 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d9062-112">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="d9062-113">특성</span><span class="sxs-lookup"><span data-stu-id="d9062-113">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="d9062-114">리플렉션(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9062-114">Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/reflection.md)
- [<span data-ttu-id="d9062-115">특성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9062-115">Attributes (Visual Basic)</span></span>](../../../../visual-basic/language-reference/attributes.md)
- [<span data-ttu-id="d9062-116">사용자 지정 특성 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9062-116">Creating Custom Attributes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="d9062-117">리플렉션을 사용하여 특성 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9062-117">Accessing Attributes by Using Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)

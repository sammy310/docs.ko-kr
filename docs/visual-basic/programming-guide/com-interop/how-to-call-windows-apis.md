---
description: '자세한 정보: 방법: Windows Api 호출 (Visual Basic)'
title: '방법: Windows API 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: ec25df3715b1f8a4612c1575b5f7192d0a133c4b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100464913"
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="39f24-103">방법: Windows API 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39f24-103">How to: Call Windows APIs (Visual Basic)</span></span>

<span data-ttu-id="39f24-104">이 예제에서는 user32.dll에서 함수를 정의 하 고 호출한 `MessageBox` 다음 문자열을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f24-104">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39f24-105">예</span><span class="sxs-lookup"><span data-stu-id="39f24-105">Example</span></span>  

 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="39f24-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="39f24-106">Compile the code</span></span>  

 <span data-ttu-id="39f24-107">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="39f24-107">This example requires:</span></span>  
  
- <span data-ttu-id="39f24-108"><xref:System> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="39f24-108">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="39f24-109">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="39f24-109">Robust Programming</span></span>  

 <span data-ttu-id="39f24-110">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="39f24-110">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="39f24-111">메서드가 정적이 아니거나, 추상 이거나, 이전에 정의 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="39f24-111">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="39f24-112">부모 형식이 인터페이스 이거나 *name* 또는 *dllName* 의 길이가 0입니다.</span><span class="sxs-lookup"><span data-stu-id="39f24-112">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="39f24-113">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="39f24-113">(<xref:System.ArgumentException>)</span></span>  
  
- <span data-ttu-id="39f24-114">*이름* 또는 *dllName* 은 `Nothing` 입니다.</span><span class="sxs-lookup"><span data-stu-id="39f24-114">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="39f24-115">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="39f24-115">(<xref:System.ArgumentNullException>)</span></span>  
  
- <span data-ttu-id="39f24-116">포함하는 형식은 `CreateType`을 사용하여 이전에 만든 것입니다.</span><span class="sxs-lookup"><span data-stu-id="39f24-116">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="39f24-117">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="39f24-117">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39f24-118">추가 정보</span><span class="sxs-lookup"><span data-stu-id="39f24-118">See also</span></span>

- [<span data-ttu-id="39f24-119">플랫폼 호출 자세히 보기</span><span class="sxs-lookup"><span data-stu-id="39f24-119">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="39f24-120">플랫폼 호출 예제</span><span class="sxs-lookup"><span data-stu-id="39f24-120">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="39f24-121">관리되지 않는 DLL 함수 사용</span><span class="sxs-lookup"><span data-stu-id="39f24-121">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- <span data-ttu-id="39f24-122">[리플렉션 내보내기를 사용하여 메서드 정의](/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="39f24-122">[Defining a Method with Reflection Emit](/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span></span>
- [<span data-ttu-id="39f24-123">연습: Windows API 호출</span><span class="sxs-lookup"><span data-stu-id="39f24-123">Walkthrough: Calling Windows APIs</span></span>](walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="39f24-124">COM Interop</span><span class="sxs-lookup"><span data-stu-id="39f24-124">COM Interop</span></span>](index.md)

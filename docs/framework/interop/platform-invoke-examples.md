---
title: 플랫폼 호출 예제
description: User32.dll에서 MessageBox 함수를 정의하고 호출하는 방법을 보여 주는 플랫폼 호출 예제를 살펴봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [.NET Framework], platform invoke
- unmanaged functions
- COM interop, platform invoke
- platform invoke, examples
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 15926806-f0b7-487e-93a6-4e9367ec689f
ms.openlocfilehash: 97b0720b8954bc24a4058e6a03c32d32bd9e3180
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620809"
---
# <a name="platform-invoke-examples"></a><span data-ttu-id="ae665-103">플랫폼 호출 예제</span><span class="sxs-lookup"><span data-stu-id="ae665-103">Platform Invoke Examples</span></span>
<span data-ttu-id="ae665-104">다음 예에서는 User32.dll에서 **MessageBox** 함수를 정의하고 호출하여 간단한 문자열을 인수로 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae665-104">The following examples demonstrate how to define and call the **MessageBox** function in User32.dll, passing a simple string as an argument.</span></span> <span data-ttu-id="ae665-105">이 예에서는 <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 필드가 **Auto**로 설정되어 있으므로 대상 플랫폼에서 문자 너비와 문자열 마샬링을 판별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae665-105">In the examples, the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field is set to **Auto** to let the target platform determine the character width and string marshaling.</span></span>  
  
 [!code-cpp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cpp/Example.cpp#1)]
 [!code-csharp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cs/Example1.cs#1)]
 [!code-vb[Conceptual.Interop.PInvoke#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Interop.PInvoke/vb/Example1.vb#1)]  
  
 <span data-ttu-id="ae665-106">추가 예제는 [플랫폼 호출을 사용하여 데이터 마샬링](marshaling-data-with-platform-invoke.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae665-106">For additional examples, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae665-107">참조</span><span class="sxs-lookup"><span data-stu-id="ae665-107">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="ae665-108">관리 코드에서 프로토타입 만들기</span><span class="sxs-lookup"><span data-stu-id="ae665-108">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="ae665-109">문자 집합 지정</span><span class="sxs-lookup"><span data-stu-id="ae665-109">Specifying a Character Set</span></span>](specifying-a-character-set.md)

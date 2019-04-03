---
title: Friend 어셈블리 참조 <reference>이(가) 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 0966cea26c5dde8f116081c7a6411b4275e50f40
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817047"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="548ab-102">Friend 어셈블리 참조 \<참조 > 올바르지 않습니다</span><span class="sxs-lookup"><span data-stu-id="548ab-102">Friend assembly reference \<reference> is invalid</span></span>
<span data-ttu-id="548ab-103">Friend 어셈블리 참조 \<참조 > 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="548ab-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="548ab-104">강력한 이름의 서명된 어셈블리는 InternalsVisibleTo 선언에 공개 키를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="548ab-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="548ab-105">어셈블리 이름을 전달 합니다 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성 생성자에는 강력한 이름의 어셈블리를 식별 하지만 포함 되지 않습니다는 `PublicKey` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="548ab-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="548ab-106">**오류 ID:** BC31535</span><span class="sxs-lookup"><span data-stu-id="548ab-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="548ab-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="548ab-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="548ab-108">Friend 강력한 이름의 어셈블리에 대 한 공개 키를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="548ab-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="548ab-109">어셈블리 이름의 부분에 전달 된 공개 키를 포함 합니다 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성 생성자를 사용 하 여는 `PublicKey` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="548ab-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="548ab-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="548ab-110">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="548ab-111">Friend 어셈블리</span><span class="sxs-lookup"><span data-stu-id="548ab-111">Friend Assemblies</span></span>](../../../standard/assembly/friend-assemblies.md)

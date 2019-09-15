---
title: Friend 어셈블리 참조 <reference>이(가) 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 6eb46c6479adc69eaf65b34c69aa69977b4d62ef
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972387"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="6a26a-102">Friend 어셈블리 참조 \<참조 > 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6a26a-102">Friend assembly reference \<reference> is invalid</span></span>
<span data-ttu-id="6a26a-103">Friend 어셈블리 참조 \<참조 > 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6a26a-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="6a26a-104">강력한 이름의 서명된 어셈블리는 InternalsVisibleTo 선언에 공개 키를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a26a-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="6a26a-105"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성 생성자에 전달 된 어셈블리 이름은 강력한 이름의 어셈블리를 식별 하지만 특성은 `PublicKey` 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a26a-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="6a26a-106">**오류 ID:** BC31535</span><span class="sxs-lookup"><span data-stu-id="6a26a-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6a26a-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="6a26a-107">To correct this error</span></span>  
  
1. <span data-ttu-id="6a26a-108">강력한 이름의 friend 어셈블리에 대 한 공개 키를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a26a-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="6a26a-109">특성을 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> `PublicKey` 사용 하 여 특성 생성자에 전달 된 어셈블리 이름의 일부로 공개 키를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a26a-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a26a-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="6a26a-110">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="6a26a-111">Friend 어셈블리</span><span class="sxs-lookup"><span data-stu-id="6a26a-111">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)

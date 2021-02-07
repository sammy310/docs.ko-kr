---
description: '자세한 정보: ICeeGen:: AddSectionReloc 메서드'
title: ICeeGen::AddSectionReloc 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.AddSectionReloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AddSectionReloc
helpviewer_keywords:
- AddSectionReloc method [.NET Framework metadata]
- ICeeGen::AddSectionReloc method [.NET Framework metadata]
ms.assetid: b500a260-1d57-4953-95e1-c27063f7c8da
topic_type:
- apiref
ms.openlocfilehash: 715c506f0bdcb3fcef33b3e9165d1f9ae47c6073
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707178"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="826f4-103">ICeeGen::AddSectionReloc 메서드</span><span class="sxs-lookup"><span data-stu-id="826f4-103">ICeeGen::AddSectionReloc Method</span></span>

<span data-ttu-id="826f4-104">코드 베이스에 .reloc 명령을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="826f4-104">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="826f4-105">이 메서드는 사용 되지 않으므로 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="826f4-105">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="826f4-106">구문</span><span class="sxs-lookup"><span data-stu-id="826f4-106">Syntax</span></span>  
  
```cpp  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,
   [in] CeeSectionRelocType    relocType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="826f4-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="826f4-107">Parameters</span></span>  

 `section`  
 <span data-ttu-id="826f4-108">진행 .Reloc 명령을 추가할 메모리 내 코드의 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="826f4-108">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="826f4-109">진행 섹션의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="826f4-109">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="826f4-110">진행 가 참조 하는 섹션 `offset` 입니다.</span><span class="sxs-lookup"><span data-stu-id="826f4-110">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="826f4-111">진행 추가할 .reloc 명령의 종류를 나타내는 [CeeSectionRelocType](ceesectionreloctype-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="826f4-111">[in] One of the [CeeSectionRelocType](ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="826f4-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="826f4-112">Requirements</span></span>  

 <span data-ttu-id="826f4-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="826f4-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="826f4-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="826f4-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="826f4-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="826f4-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="826f4-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="826f4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="826f4-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="826f4-117">See also</span></span>

- [<span data-ttu-id="826f4-118">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="826f4-118">ICeeGen Interface</span></span>](iceegen-interface.md)

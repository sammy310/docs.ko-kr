---
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
ms.openlocfilehash: 129750644962cee3206b9e38cbeaa77d38dddd71
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176112"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="3d866-102">ICeeGen::AddSectionReloc 메서드</span><span class="sxs-lookup"><span data-stu-id="3d866-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="3d866-103">코드 베이스에 .reloc 명령을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3d866-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="3d866-104">이 메서드는 더 이상 사용되지 않으며 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d866-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d866-105">구문</span><span class="sxs-lookup"><span data-stu-id="3d866-105">Syntax</span></span>  
  
```cpp  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,
   [in] CeeSectionRelocType    relocType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d866-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3d866-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="3d866-107">【인】 .reloc 명령을 추가할 메모리 내 코드 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="3d866-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="3d866-108">【인】 단면의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="3d866-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="3d866-109">【인】 참조하는 `offset` 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="3d866-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="3d866-110">【인】 [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) 값 중 하나, 추가할 .reloc 명령의 종류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3d866-110">[in] One of the [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d866-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3d866-111">Requirements</span></span>  
 <span data-ttu-id="3d866-112">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d866-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d866-113">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="3d866-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3d866-114">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="3d866-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3d866-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d866-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d866-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d866-116">See also</span></span>

- [<span data-ttu-id="3d866-117">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d866-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

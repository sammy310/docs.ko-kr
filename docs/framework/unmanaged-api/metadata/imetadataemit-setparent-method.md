---
title: IMetaDataEmit::SetParent 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParent
helpviewer_keywords:
- SetParent method [.NET Framework metadata]
- IMetaDataEmit::SetParent method [.NET Framework metadata]
ms.assetid: 02a02ff7-ae0e-4692-a20e-372405f23052
topic_type:
- apiref
ms.openlocfilehash: cef817b52718acfbc4360e9d3742a5a78abd3afe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675050"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="15324-102">IMetaDataEmit::SetParent 메서드</span><span class="sxs-lookup"><span data-stu-id="15324-102">IMetaDataEmit::SetParent Method</span></span>

<span data-ttu-id="15324-103">[IMetaDataEmit::D efinememberref](imetadataemit-definememberref-method.md)에 대 한 이전 호출로 정의 된 지정 된 멤버가 [IMetaDataEmit::D Efin def](imetadataemit-definetypedef-method.md)의 이전 호출에 정의 된 대로 지정 된 형식의 멤버 임을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="15324-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15324-104">구문</span><span class="sxs-lookup"><span data-stu-id="15324-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15324-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="15324-105">Parameters</span></span>  

 `mr`  
 <span data-ttu-id="15324-106">진행 `mdMemberRef` 새 부모를 받을 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="15324-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="15324-107">진행 `mdToken` 새 부모에 대 한입니다.</span><span class="sxs-lookup"><span data-stu-id="15324-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15324-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="15324-108">Requirements</span></span>  

 <span data-ttu-id="15324-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="15324-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15324-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="15324-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="15324-111">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15324-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15324-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15324-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15324-113">참조</span><span class="sxs-lookup"><span data-stu-id="15324-113">See also</span></span>

- [<span data-ttu-id="15324-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15324-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="15324-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15324-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

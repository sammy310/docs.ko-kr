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
ms.openlocfilehash: 7389e9233fd946cdb2c810bec01cfbfffc8b707d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175605"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="d2271-102">IMetaDataEmit::SetParent 메서드</span><span class="sxs-lookup"><span data-stu-id="d2271-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="d2271-103">[IMetaDataEmit::DefineMemberRef에](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)대한 사전 호출에 의해 정의된 지정된 멤버가 [IMetaDataEmit::DefineTypeDef에](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)대한 사전 호출에 정의된 대로 지정된 형식의 멤버임을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2271-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2271-104">구문</span><span class="sxs-lookup"><span data-stu-id="d2271-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2271-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d2271-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="d2271-106">【인】 새 `mdMemberRef` 부모를 받을 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d2271-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="d2271-107">【인】 새 `mdToken` 상위에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d2271-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2271-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d2271-108">Requirements</span></span>  
 <span data-ttu-id="d2271-109">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2271-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2271-110">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="d2271-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d2271-111">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="d2271-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2271-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2271-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2271-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2271-113">See also</span></span>

- [<span data-ttu-id="d2271-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2271-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d2271-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2271-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

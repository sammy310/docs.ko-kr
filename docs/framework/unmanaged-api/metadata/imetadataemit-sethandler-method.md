---
title: IMetaDataEmit::SetHandler 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetHandler
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type:
- apiref
ms.openlocfilehash: 6737275fb77e6f177832eb1d96214c37942bcd22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442159"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="07720-102">IMetaDataEmit::SetHandler 메서드</span><span class="sxs-lookup"><span data-stu-id="07720-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="07720-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span><span class="sxs-lookup"><span data-stu-id="07720-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07720-104">구문</span><span class="sxs-lookup"><span data-stu-id="07720-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07720-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="07720-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="07720-106">[in] The handler to register.</span><span class="sxs-lookup"><span data-stu-id="07720-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07720-107">주의</span><span class="sxs-lookup"><span data-stu-id="07720-107">Remarks</span></span>  
 <span data-ttu-id="07720-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span><span class="sxs-lookup"><span data-stu-id="07720-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="07720-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span><span class="sxs-lookup"><span data-stu-id="07720-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07720-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="07720-110">Requirements</span></span>  
 <span data-ttu-id="07720-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07720-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07720-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="07720-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="07720-113">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="07720-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="07720-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07720-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07720-115">참조</span><span class="sxs-lookup"><span data-stu-id="07720-115">See also</span></span>

- [<span data-ttu-id="07720-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="07720-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="07720-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="07720-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

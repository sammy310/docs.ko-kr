---
title: IMetaDataEmit::SetMethodImplFlags 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodImplFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodImplFlags
helpviewer_keywords:
- IMetaDataEmit::SetMethodImplFlags method [.NET Framework metadata]
- SetMethodImpFlags method [.NET Framework metadata]
ms.assetid: 4bc82d9b-9544-4be3-ba51-a2d4d806158a
topic_type:
- apiref
ms.openlocfilehash: b8755629cca27784609de8166dddf44ed1c82bdc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432543"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="ff8b9-102">IMetaDataEmit::SetMethodImplFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="ff8b9-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="ff8b9-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span><span class="sxs-lookup"><span data-stu-id="ff8b9-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff8b9-104">구문</span><span class="sxs-lookup"><span data-stu-id="ff8b9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodImplFlags (   
    [in]  mdMethodDef   md,   
    [in]  DWORD         dwImplFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff8b9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ff8b9-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="ff8b9-106">[in] The token for the method to be changed.</span><span class="sxs-lookup"><span data-stu-id="ff8b9-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="ff8b9-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span><span class="sxs-lookup"><span data-stu-id="ff8b9-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff8b9-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff8b9-108">Requirements</span></span>  
 <span data-ttu-id="ff8b9-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff8b9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff8b9-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ff8b9-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ff8b9-111">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ff8b9-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff8b9-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff8b9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff8b9-113">참조</span><span class="sxs-lookup"><span data-stu-id="ff8b9-113">See also</span></span>

- [<span data-ttu-id="ff8b9-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff8b9-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ff8b9-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff8b9-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

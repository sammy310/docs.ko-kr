---
title: IMetaDataEmit2::GetDeltaSaveSize 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.GetDeltaSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::GetDeltaSaveSize
helpviewer_keywords:
- IMetaDataEmit2::GetDeltaSaveSize method [.NET Framework metadata]
- GetDeltaSaveSize method [.NET Framework metadata]
ms.assetid: 036db5e7-8211-4645-9a34-03d1a89be955
topic_type:
- apiref
ms.openlocfilehash: 219d3196e3b2125033a23623b7e77e31c6f1ff03
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440490"
---
# <a name="imetadataemit2getdeltasavesize-method"></a><span data-ttu-id="021e3-102">IMetaDataEmit2::GetDeltaSaveSize 메서드</span><span class="sxs-lookup"><span data-stu-id="021e3-102">IMetaDataEmit2::GetDeltaSaveSize Method</span></span>
<span data-ttu-id="021e3-103">Gets a value indicating any change in metadata size that results from the current edit-and-continue session.</span><span class="sxs-lookup"><span data-stu-id="021e3-103">Gets a value indicating any change in metadata size that results from the current edit-and-continue session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="021e3-104">구문</span><span class="sxs-lookup"><span data-stu-id="021e3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="021e3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="021e3-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="021e3-106">[in] One of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) values, indicating the level of precision desired.</span><span class="sxs-lookup"><span data-stu-id="021e3-106">[in] One of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) values, indicating the level of precision desired.</span></span> <span data-ttu-id="021e3-107">For the .NET Framework version 2.0, this parameter is ignored.</span><span class="sxs-lookup"><span data-stu-id="021e3-107">For the .NET Framework version 2.0, this parameter is ignored.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="021e3-108">[out] The change in the size of the metadata.</span><span class="sxs-lookup"><span data-stu-id="021e3-108">[out] The change in the size of the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="021e3-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="021e3-109">Requirements</span></span>  
 <span data-ttu-id="021e3-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="021e3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="021e3-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="021e3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="021e3-112">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="021e3-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="021e3-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="021e3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="021e3-114">참조</span><span class="sxs-lookup"><span data-stu-id="021e3-114">See also</span></span>

- [<span data-ttu-id="021e3-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="021e3-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="021e3-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="021e3-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)

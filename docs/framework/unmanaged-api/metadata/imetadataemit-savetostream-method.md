---
title: IMetaDataEmit::SaveToStream 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToStream
helpviewer_keywords:
- IMetaDataEmit::SaveToStream method [.NET Framework metadata]
- SaveToStream method [.NET Framework metadata]
ms.assetid: e0290a49-3818-4a43-ad46-3014faa34f97
topic_type:
- apiref
ms.openlocfilehash: 23f6186b2561cbcd52db767616d986084f33860b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435933"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="8eef7-102">IMetaDataEmit::SaveToStream 메서드</span><span class="sxs-lookup"><span data-stu-id="8eef7-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="8eef7-103">Saves all metadata in the current scope to the specified `IStream`.</span><span class="sxs-lookup"><span data-stu-id="8eef7-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eef7-104">구문</span><span class="sxs-lookup"><span data-stu-id="8eef7-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToStream (   
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8eef7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8eef7-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="8eef7-106">[in] The writable stream to save to.</span><span class="sxs-lookup"><span data-stu-id="8eef7-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="8eef7-107">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eef7-107">[in] Reserved.</span></span> <span data-ttu-id="8eef7-108">Must be zero.</span><span class="sxs-lookup"><span data-stu-id="8eef7-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8eef7-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8eef7-109">Requirements</span></span>  
 <span data-ttu-id="8eef7-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8eef7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8eef7-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8eef7-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8eef7-112">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8eef7-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8eef7-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8eef7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eef7-114">참조</span><span class="sxs-lookup"><span data-stu-id="8eef7-114">See also</span></span>

- [<span data-ttu-id="8eef7-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8eef7-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8eef7-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8eef7-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

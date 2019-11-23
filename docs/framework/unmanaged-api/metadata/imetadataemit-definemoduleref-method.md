---
title: IMetaDataEmit::DefineModuleRef 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineModuleRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineModuleRef
helpviewer_keywords:
- DefineModuleRef method [.NET Framework metadata]
- IMetaDataEmit::DefineModuleRef method [.NET Framework metadata]
ms.assetid: f2833594-d90b-4a71-9a53-34b12470c64a
topic_type:
- apiref
ms.openlocfilehash: c736eccfd5d05ec9b65e6ed26187e7c7b4387c5d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431734"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="4ae77-102">IMetaDataEmit::DefineModuleRef 메서드</span><span class="sxs-lookup"><span data-stu-id="4ae77-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="4ae77-103">Creates the metadata signature for a module with the specified name.</span><span class="sxs-lookup"><span data-stu-id="4ae77-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ae77-104">구문</span><span class="sxs-lookup"><span data-stu-id="4ae77-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineModuleRef (     
    [in]  LPCWSTR           szName,   
    [out] mdModuleRef       *pmur   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ae77-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4ae77-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="4ae77-106">[in] The name of the other metadata file, typically a DLL.</span><span class="sxs-lookup"><span data-stu-id="4ae77-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="4ae77-107">This is the file name only.</span><span class="sxs-lookup"><span data-stu-id="4ae77-107">This is the file name only.</span></span> <span data-ttu-id="4ae77-108">Do not use a full path name.</span><span class="sxs-lookup"><span data-stu-id="4ae77-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="4ae77-109">[out] The assigned `mdModuleRef` token.</span><span class="sxs-lookup"><span data-stu-id="4ae77-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ae77-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4ae77-110">Requirements</span></span>  
 <span data-ttu-id="4ae77-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ae77-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ae77-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4ae77-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4ae77-113">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4ae77-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4ae77-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ae77-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ae77-115">참조</span><span class="sxs-lookup"><span data-stu-id="4ae77-115">See also</span></span>

- [<span data-ttu-id="4ae77-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ae77-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4ae77-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ae77-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

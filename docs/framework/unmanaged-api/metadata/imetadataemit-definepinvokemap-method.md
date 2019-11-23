---
title: IMetaDataEmit::DefinePinvokeMap 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePinvokeMap
helpviewer_keywords:
- DefinePinvokeMap method [.NET Framework metadata]
- IMetaDataEmit::DefinePinvokeMap method [.NET Framework metadata]
ms.assetid: 03abf921-5154-4070-88fa-10b7092901fb
topic_type:
- apiref
ms.openlocfilehash: 9d4ea16a212ac5f0120d63510f07eaee69af739e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431481"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="db2d7-102">IMetaDataEmit::DefinePinvokeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="db2d7-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>
<span data-ttu-id="db2d7-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span><span class="sxs-lookup"><span data-stu-id="db2d7-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db2d7-104">구문</span><span class="sxs-lookup"><span data-stu-id="db2d7-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePinvokeMap (   
    [in]  mdToken            tk,   
    [in]  DWORD              dwMappingFlags,   
    [in]  LPCWSTR            szImportName,   
    [in]  mdModuleRef        mrImportDLL   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db2d7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="db2d7-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="db2d7-106">[in] The token for the target method.</span><span class="sxs-lookup"><span data-stu-id="db2d7-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="db2d7-107">[in] Flags used by PInvoke to do the mapping.</span><span class="sxs-lookup"><span data-stu-id="db2d7-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="db2d7-108">[in] The name of the target export method in an unmanaged DLL.</span><span class="sxs-lookup"><span data-stu-id="db2d7-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="db2d7-109">[in] The token for the target native DLL.</span><span class="sxs-lookup"><span data-stu-id="db2d7-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db2d7-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="db2d7-110">Requirements</span></span>  
 <span data-ttu-id="db2d7-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="db2d7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db2d7-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="db2d7-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="db2d7-113">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="db2d7-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db2d7-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db2d7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db2d7-115">참조</span><span class="sxs-lookup"><span data-stu-id="db2d7-115">See also</span></span>

- [<span data-ttu-id="db2d7-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db2d7-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="db2d7-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db2d7-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

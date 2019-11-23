---
title: IMetaDataEmit::SetPinvokeMap 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPinvokeMap
helpviewer_keywords:
- IMetaDataEmit::SetPinvokeMap method [.NET Framework metadata]
- SetPinvokeMap method [.NET Framework metadata]
ms.assetid: c6bfd574-1da3-4ba7-82f2-46ca5efcbaba
topic_type:
- apiref
ms.openlocfilehash: 4e2a78e2d049e952aa1be0b3a8fd640eb18d0320
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440575"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="cd1d7-102">IMetaDataEmit::SetPinvokeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="cd1d7-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="cd1d7-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span><span class="sxs-lookup"><span data-stu-id="cd1d7-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd1d7-104">구문</span><span class="sxs-lookup"><span data-stu-id="cd1d7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPinvokeMap (   
    [in]  mdToken      tk,   
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,   
    [in]  mdModuleRef  mrImportDLL   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd1d7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cd1d7-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="cd1d7-106">[in] The `mdToken` to which mapping information applies.</span><span class="sxs-lookup"><span data-stu-id="cd1d7-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="cd1d7-107">[in] Flags used by PInvoke to do the mapping.</span><span class="sxs-lookup"><span data-stu-id="cd1d7-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="cd1d7-108">This is a bitmask of `CorPinvokeMap` values.</span><span class="sxs-lookup"><span data-stu-id="cd1d7-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="cd1d7-109">[in] The name of the target export in the native DLL.</span><span class="sxs-lookup"><span data-stu-id="cd1d7-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="cd1d7-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span><span class="sxs-lookup"><span data-stu-id="cd1d7-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd1d7-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd1d7-111">Requirements</span></span>  
 <span data-ttu-id="cd1d7-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd1d7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd1d7-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cd1d7-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cd1d7-114">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cd1d7-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd1d7-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd1d7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd1d7-116">참조</span><span class="sxs-lookup"><span data-stu-id="cd1d7-116">See also</span></span>

- [<span data-ttu-id="cd1d7-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cd1d7-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="cd1d7-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cd1d7-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b838a83a160707e546b05ef334eb17d0c6e6cc27
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133564"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="fb2ee-102">IMetaDataEmit::SetPinvokeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="fb2ee-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="fb2ee-103">설정 하거나 이전 호출에서 정의 된 대로 메서드의 PInvoke 서명 기능을 변경 [imetadataemit:: Definepinvokemap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ee-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb2ee-104">구문</span><span class="sxs-lookup"><span data-stu-id="fb2ee-104">Syntax</span></span>  
  
```  
HRESULT SetPinvokeMap (   
    [in]  mdToken      tk,   
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,   
    [in]  mdModuleRef  mrImportDLL   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb2ee-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fb2ee-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="fb2ee-106">[in] `mdToken` 정보가 적용 되는 매핑.</span><span class="sxs-lookup"><span data-stu-id="fb2ee-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="fb2ee-107">[in] PInvoke 하는 매핑을 수행 하는 데 사용 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ee-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="fb2ee-108">이 비트 마스크의 `CorPinvokeMap` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ee-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="fb2ee-109">[in] 네이티브 DLL의 내보내기 대상의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ee-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="fb2ee-110">[in] `mdModuleRef` 대상에 대 한 토큰 DLL을 관리 되지 않는 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2ee-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb2ee-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb2ee-111">Requirements</span></span>  
 <span data-ttu-id="fb2ee-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fb2ee-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb2ee-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fb2ee-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fb2ee-114">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="fb2ee-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb2ee-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb2ee-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb2ee-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="fb2ee-116">See also</span></span>

- [<span data-ttu-id="fb2ee-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb2ee-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="fb2ee-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb2ee-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

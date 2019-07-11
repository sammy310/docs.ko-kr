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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6421ca47c3439d94c1ae86caaf2198298872d53
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777526"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="672b6-102">IMetaDataEmit::DefinePinvokeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="672b6-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>
<span data-ttu-id="672b6-103">지정한 토큰이 참조 하는 메서드 서명의 PInvoke의 기능을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="672b6-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="672b6-104">구문</span><span class="sxs-lookup"><span data-stu-id="672b6-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePinvokeMap (   
    [in]  mdToken            tk,   
    [in]  DWORD              dwMappingFlags,   
    [in]  LPCWSTR            szImportName,   
    [in]  mdModuleRef        mrImportDLL   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="672b6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="672b6-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="672b6-106">[in] 대상 메서드에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="672b6-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="672b6-107">[in] PInvoke 하는 매핑을 수행 하는 데 사용 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="672b6-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="672b6-108">[in] 대상의 이름을 관리 되지 않는 DLL에서 메서드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="672b6-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="672b6-109">[in] 대상에 대 한 토큰 네이티브 DLL입니다.</span><span class="sxs-lookup"><span data-stu-id="672b6-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="672b6-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="672b6-110">Requirements</span></span>  
 <span data-ttu-id="672b6-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="672b6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="672b6-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="672b6-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="672b6-113">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="672b6-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="672b6-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="672b6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="672b6-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="672b6-115">See also</span></span>

- [<span data-ttu-id="672b6-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="672b6-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="672b6-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="672b6-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

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
ms.openlocfilehash: e414bc5a7d537e8d153541f05b22dd91578e8739
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177749"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="0075d-102">IMetaDataEmit::DefinePinvokeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="0075d-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>
<span data-ttu-id="0075d-103">지정된 토큰에서 참조하는 메서드의 PInvoke 서명의 기능을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0075d-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0075d-104">구문</span><span class="sxs-lookup"><span data-stu-id="0075d-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePinvokeMap (
    [in]  mdToken            tk,
    [in]  DWORD              dwMappingFlags,
    [in]  LPCWSTR            szImportName,
    [in]  mdModuleRef        mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0075d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0075d-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="0075d-106">【인】 대상 메서드에 대한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0075d-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="0075d-107">【인】 PInvoke가 매핑을 수행하는 데 사용하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="0075d-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="0075d-108">【인】 관리되지 않는 DLL에서 대상 내보내기 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0075d-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="0075d-109">【인】 대상 네이티브 DLL에 대한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0075d-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0075d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0075d-110">Requirements</span></span>  
 <span data-ttu-id="0075d-111">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0075d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0075d-112">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="0075d-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0075d-113">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="0075d-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0075d-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0075d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0075d-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0075d-115">See also</span></span>

- [<span data-ttu-id="0075d-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0075d-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0075d-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0075d-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

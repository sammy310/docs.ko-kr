---
description: IMetaDataEmit::D efinePinvokeMap 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 7b0477ca603241e773a67f335da579daa2ed3d30
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784069"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="b0bd3-103">IMetaDataEmit::DefinePinvokeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="b0bd3-103">IMetaDataEmit::DefinePinvokeMap Method</span></span>

<span data-ttu-id="b0bd3-104">지정 된 토큰이 참조 하는 메서드에 대 한 PInvoke 시그니처의 기능을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-104">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0bd3-105">구문</span><span class="sxs-lookup"><span data-stu-id="b0bd3-105">Syntax</span></span>  
  
```cpp  
HRESULT DefinePinvokeMap (
    [in]  mdToken            tk,
    [in]  DWORD              dwMappingFlags,
    [in]  LPCWSTR            szImportName,
    [in]  mdModuleRef        mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0bd3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b0bd3-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="b0bd3-107">진행 대상 메서드에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-107">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="b0bd3-108">진행 PInvoke에서 매핑을 수행 하는 데 사용 되는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-108">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="b0bd3-109">진행 관리 되지 않는 DLL의 대상 내보내기 메서드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-109">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="b0bd3-110">진행 대상 네이티브 DLL의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-110">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0bd3-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b0bd3-111">Requirements</span></span>  

 <span data-ttu-id="b0bd3-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0bd3-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="b0bd3-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b0bd3-114">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b0bd3-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0bd3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0bd3-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0bd3-116">See also</span></span>

- [<span data-ttu-id="b0bd3-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0bd3-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="b0bd3-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0bd3-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

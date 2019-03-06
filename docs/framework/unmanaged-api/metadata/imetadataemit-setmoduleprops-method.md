---
title: IMetaDataEmit::SetModuleProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetModuleProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetModuleProps
helpviewer_keywords:
- SetModuleProps method [.NET Framework metadata]
- IMetaDataEmit::SetModuleProps method [.NET Framework metadata]
ms.assetid: b74d7629-5f46-458f-8d67-2456a1e7030c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5219a414c5961128d4eaa27c1f18d635938dc5ba
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497407"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="4a06a-102">IMetaDataEmit::SetModuleProps 메서드</span><span class="sxs-lookup"><span data-stu-id="4a06a-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="4a06a-103">에 대 한 이전 호출에서 정의 된 모듈에 대 한 참조를 업데이트 [imetadataemit:: Definemoduleref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4a06a-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a06a-104">구문</span><span class="sxs-lookup"><span data-stu-id="4a06a-104">Syntax</span></span>  
  
```  
HRESULT SetModuleProps (   
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a06a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4a06a-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="4a06a-106">[in] 유니코드에서 모듈 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4a06a-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="4a06a-107">파일 이름만 및 전체 경로 이름이 아닌 경우</span><span class="sxs-lookup"><span data-stu-id="4a06a-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a06a-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a06a-108">Requirements</span></span>  
 <span data-ttu-id="4a06a-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a06a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a06a-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4a06a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4a06a-111">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="4a06a-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a06a-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a06a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a06a-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="4a06a-113">See also</span></span>
- [<span data-ttu-id="4a06a-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a06a-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4a06a-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a06a-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

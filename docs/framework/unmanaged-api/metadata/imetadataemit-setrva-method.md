---
title: IMetaDataEmit::SetRVA 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e17a6846ba0276ec7ba423ab25e3f11baf278d03
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59098756"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="9216a-102">IMetaDataEmit::SetRVA 메서드</span><span class="sxs-lookup"><span data-stu-id="9216a-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="9216a-103">지정 된 메서드의 상대 가상 주소를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9216a-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9216a-104">구문</span><span class="sxs-lookup"><span data-stu-id="9216a-104">Syntax</span></span>  
  
```  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9216a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9216a-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="9216a-106">[in] 대상 메서드 또는 메서드 구현에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="9216a-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="9216a-107">[in] 주소는 코드 또는 데이터 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="9216a-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9216a-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9216a-108">Requirements</span></span>  
 <span data-ttu-id="9216a-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9216a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9216a-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9216a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9216a-111">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="9216a-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9216a-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9216a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9216a-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="9216a-113">See also</span></span>

- [<span data-ttu-id="9216a-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9216a-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="9216a-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9216a-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

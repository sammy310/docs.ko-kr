---
title: IMetaDataEmit::SetFieldRVA 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldRVA
helpviewer_keywords:
- IMetaDataEmit::SetFieldRVA method [.NET Framework metadata]
- SetFieldRVA method [.NET Framework metadata]
ms.assetid: 6dc37f9d-87ee-4cb3-9216-ced600184ce8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 93ca394eb877a86e4242d5f9f18eb26f5628db7e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751082"
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="5cfaf-102">IMetaDataEmit::SetFieldRVA 메서드</span><span class="sxs-lookup"><span data-stu-id="5cfaf-102">IMetaDataEmit::SetFieldRVA Method</span></span>
<span data-ttu-id="5cfaf-103">지정한 토큰이 참조 하는 필드의 상대 가상 주소에 대 한 전역 변수 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfaf-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cfaf-104">구문</span><span class="sxs-lookup"><span data-stu-id="5cfaf-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldRVA (   
    [in]  mdFieldDef  fd,   
    [in]  ULONG       ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cfaf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5cfaf-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="5cfaf-106">[in] 대상 필드에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5cfaf-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="5cfaf-107">[in] 코드 또는 데이터 영역의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="5cfaf-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cfaf-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5cfaf-108">Requirements</span></span>  
 <span data-ttu-id="5cfaf-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5cfaf-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cfaf-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5cfaf-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5cfaf-111">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="5cfaf-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5cfaf-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cfaf-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cfaf-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="5cfaf-113">See also</span></span>

- [<span data-ttu-id="5cfaf-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5cfaf-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="5cfaf-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5cfaf-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

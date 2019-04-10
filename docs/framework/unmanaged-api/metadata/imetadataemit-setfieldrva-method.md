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
ms.openlocfilehash: 4ebde1d506a120a99e1c637c660b45d698994f5a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181677"
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="25d2b-102">IMetaDataEmit::SetFieldRVA 메서드</span><span class="sxs-lookup"><span data-stu-id="25d2b-102">IMetaDataEmit::SetFieldRVA Method</span></span>
<span data-ttu-id="25d2b-103">지정한 토큰이 참조 하는 필드의 상대 가상 주소에 대 한 전역 변수 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d2b-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25d2b-104">구문</span><span class="sxs-lookup"><span data-stu-id="25d2b-104">Syntax</span></span>  
  
```  
HRESULT SetFieldRVA (   
    [in]  mdFieldDef  fd,   
    [in]  ULONG       ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25d2b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="25d2b-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="25d2b-106">[in] 대상 필드에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="25d2b-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="25d2b-107">[in] 코드 또는 데이터 영역의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="25d2b-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25d2b-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="25d2b-108">Requirements</span></span>  
 <span data-ttu-id="25d2b-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="25d2b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25d2b-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="25d2b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="25d2b-111">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="25d2b-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="25d2b-112">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="25d2b-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="25d2b-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="25d2b-113">See also</span></span>

- [<span data-ttu-id="25d2b-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25d2b-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="25d2b-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25d2b-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

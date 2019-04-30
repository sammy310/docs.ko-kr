---
title: IMetaDataEmit::SetMethodImplFlags 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodImplFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodImplFlags
helpviewer_keywords:
- IMetaDataEmit::SetMethodImplFlags method [.NET Framework metadata]
- SetMethodImpFlags method [.NET Framework metadata]
ms.assetid: 4bc82d9b-9544-4be3-ba51-a2d4d806158a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 28c0aa37bdcae2a09a4d53f920efd3ffe7117bd3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992461"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="aa596-102">IMetaDataEmit::SetMethodImplFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="aa596-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="aa596-103">설정 하거나 지정된 된 토큰에서 참조 되는 상속 된 메서드 구현의 메타 데이터 서명을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa596-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa596-104">구문</span><span class="sxs-lookup"><span data-stu-id="aa596-104">Syntax</span></span>  
  
```  
HRESULT SetMethodImplFlags (   
    [in]  mdMethodDef   md,   
    [in]  DWORD         dwImplFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa596-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aa596-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="aa596-106">[in] 변경 방법에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="aa596-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="aa596-107">[in] 값을 조합 합니다 [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) 메서드 구현 기능을 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="aa596-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa596-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa596-108">Requirements</span></span>  
 <span data-ttu-id="aa596-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="aa596-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa596-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="aa596-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aa596-111">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="aa596-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa596-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa596-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa596-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="aa596-113">See also</span></span>

- [<span data-ttu-id="aa596-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa596-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="aa596-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa596-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

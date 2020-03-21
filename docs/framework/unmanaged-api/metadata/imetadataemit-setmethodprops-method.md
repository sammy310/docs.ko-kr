---
title: IMetaDataEmit::SetMethodProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodProps
helpviewer_keywords:
- SetMethodProps method [.NET Framework metadata]
- IMetaDataEmit::SetMethodProps method [.NET Framework metadata]
ms.assetid: e0c6ac12-22ea-43f5-b799-8cda0faf3336
topic_type:
- apiref
ms.openlocfilehash: 9662a14b4ea97aed16968083489324d46c38dda2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177520"
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="662cb-102">IMetaDataEmit::SetMethodProps 메서드</span><span class="sxs-lookup"><span data-stu-id="662cb-102">IMetaDataEmit::SetMethodProps Method</span></span>
<span data-ttu-id="662cb-103">[IMetaDataEmit::DefineMethod에](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)대한 사전 호출에 의해 정의된 메서드의 지정된 상대 가상 주소에 저장된 기능을 설정하거나 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="662cb-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="662cb-104">구문</span><span class="sxs-lookup"><span data-stu-id="662cb-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodProps (
    [in]  mdMethodDef md,
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,
    [in]  DWORD       dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="662cb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="662cb-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="662cb-106">【인】 변경할 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="662cb-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="662cb-107">【인】 멤버 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="662cb-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="662cb-108">【인】 코드의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="662cb-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="662cb-109">【인】 메서드에 대 한 구현 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="662cb-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="662cb-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="662cb-110">Requirements</span></span>  
 <span data-ttu-id="662cb-111">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="662cb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="662cb-112">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="662cb-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="662cb-113">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="662cb-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="662cb-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="662cb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="662cb-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="662cb-115">See also</span></span>

- [<span data-ttu-id="662cb-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="662cb-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="662cb-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="662cb-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

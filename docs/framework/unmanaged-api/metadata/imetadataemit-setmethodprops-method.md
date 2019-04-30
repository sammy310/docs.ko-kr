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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 534afdd5990435c6b4db5ef8ea27a8065b199496
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050014"
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="1fbb9-102">IMetaDataEmit::SetMethodProps 메서드</span><span class="sxs-lookup"><span data-stu-id="1fbb9-102">IMetaDataEmit::SetMethodProps Method</span></span>
<span data-ttu-id="1fbb9-103">설정 하거나 지정된 된 상대 가상 주소에 대 한 이전 호출에서 정의 된 메서드의 저장 하는 기능을 업데이트 [imetadataemit:: Definemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1fbb9-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fbb9-104">구문</span><span class="sxs-lookup"><span data-stu-id="1fbb9-104">Syntax</span></span>  
  
```  
HRESULT SetMethodProps (   
    [in]  mdMethodDef md,   
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,   
    [in]  DWORD       dwImplFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fbb9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1fbb9-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="1fbb9-106">[in] 변경 방법에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="1fbb9-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="1fbb9-107">[in] 멤버 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1fbb9-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="1fbb9-108">[in] 코드의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1fbb9-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="1fbb9-109">[in] 메서드에 대 한 구현 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="1fbb9-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fbb9-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1fbb9-110">Requirements</span></span>  
 <span data-ttu-id="1fbb9-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1fbb9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fbb9-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1fbb9-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1fbb9-113">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="1fbb9-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1fbb9-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fbb9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fbb9-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="1fbb9-115">See also</span></span>

- [<span data-ttu-id="1fbb9-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1fbb9-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="1fbb9-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1fbb9-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

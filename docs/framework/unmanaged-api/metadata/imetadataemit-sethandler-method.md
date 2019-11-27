---
title: IMetaDataEmit::SetHandler 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetHandler
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type:
- apiref
ms.openlocfilehash: 6737275fb77e6f177832eb1d96214c37942bcd22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442159"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="3680a-102">IMetaDataEmit::SetHandler 메서드</span><span class="sxs-lookup"><span data-stu-id="3680a-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="3680a-103">지정 된 `IUnknown` 포인터에서 참조 하는 메서드를 토큰 다시 매핑에 대 한 알림 콜백으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3680a-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3680a-104">구문</span><span class="sxs-lookup"><span data-stu-id="3680a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3680a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3680a-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="3680a-106">진행 등록할 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="3680a-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3680a-107">설명</span><span class="sxs-lookup"><span data-stu-id="3680a-107">Remarks</span></span>  
 <span data-ttu-id="3680a-108">메타 데이터 엔진은 `SetHandler`에서 제공 하는 메서드를 사용 하 여 최적화 된 방식으로 레코드를 생성 하지 않고 저장 된 레코드를 최적화 하는 컴파일러로 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3680a-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="3680a-109">`SetHandler`를 통해 콜백 메서드를 제공 하지 않는 경우 각 범위에 대해 병합 시 `IMapToken`를 사용 하 여 여러 가져오기 범위가 병합 된 경우를 제외 하 고는 저장 시 최적화가 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3680a-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3680a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3680a-110">Requirements</span></span>  
 <span data-ttu-id="3680a-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3680a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3680a-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="3680a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3680a-113">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3680a-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3680a-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3680a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3680a-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="3680a-115">See also</span></span>

- [<span data-ttu-id="3680a-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3680a-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3680a-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3680a-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

---
description: '자세히 알아보기: IMetaDataError 인터페이스'
title: IMetaDataError 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError
helpviewer_keywords:
- IMetaDataError interface [.NET Framework metadata]
ms.assetid: 0020b62c-ea88-40c7-a9ee-16b064f81624
topic_type:
- apiref
ms.openlocfilehash: f32c8abc3cccce770b86ce47016d9b7e18acad23
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771693"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="228cc-103">IMetaDataError 인터페이스</span><span class="sxs-lookup"><span data-stu-id="228cc-103">IMetaDataError Interface</span></span>

<span data-ttu-id="228cc-104">메타 데이터 병합 중에 오류를 보고 하는 콜백 메커니즘을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="228cc-104">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="228cc-105">`IMetaDataError`인터페이스는 클라이언트에 의해 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="228cc-105">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="228cc-106">메서드</span><span class="sxs-lookup"><span data-stu-id="228cc-106">Methods</span></span>  
  
|<span data-ttu-id="228cc-107">메서드</span><span class="sxs-lookup"><span data-stu-id="228cc-107">Method</span></span>|<span data-ttu-id="228cc-108">설명</span><span class="sxs-lookup"><span data-stu-id="228cc-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="228cc-109">OnError 메서드</span><span class="sxs-lookup"><span data-stu-id="228cc-109">OnError Method</span></span>](imetadataerror-onerror-method.md)|<span data-ttu-id="228cc-110">메타 데이터 병합 중에 발생 하는 오류에 대 한 알림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="228cc-110">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="228cc-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="228cc-111">Requirements</span></span>  

 <span data-ttu-id="228cc-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="228cc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="228cc-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="228cc-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="228cc-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="228cc-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="228cc-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="228cc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="228cc-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="228cc-116">See also</span></span>

- [<span data-ttu-id="228cc-117">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="228cc-117">Metadata Interfaces</span></span>](metadata-interfaces.md)

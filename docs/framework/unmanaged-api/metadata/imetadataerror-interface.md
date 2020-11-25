---
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
ms.openlocfilehash: 5f5e04787ce0ab0e1c8ecf3c19ba37e76ba38bfe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701928"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="b8d34-102">IMetaDataError 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b8d34-102">IMetaDataError Interface</span></span>

<span data-ttu-id="b8d34-103">메타 데이터 병합 중에 오류를 보고 하는 콜백 메커니즘을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8d34-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b8d34-104">`IMetaDataError`인터페이스는 클라이언트에 의해 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8d34-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b8d34-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b8d34-105">Methods</span></span>  
  
|<span data-ttu-id="b8d34-106">메서드</span><span class="sxs-lookup"><span data-stu-id="b8d34-106">Method</span></span>|<span data-ttu-id="b8d34-107">설명</span><span class="sxs-lookup"><span data-stu-id="b8d34-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b8d34-108">OnError 메서드</span><span class="sxs-lookup"><span data-stu-id="b8d34-108">OnError Method</span></span>](imetadataerror-onerror-method.md)|<span data-ttu-id="b8d34-109">메타 데이터 병합 중에 발생 하는 오류에 대 한 알림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8d34-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b8d34-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b8d34-110">Requirements</span></span>  

 <span data-ttu-id="b8d34-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8d34-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8d34-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="b8d34-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b8d34-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8d34-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b8d34-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8d34-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8d34-115">참조</span><span class="sxs-lookup"><span data-stu-id="b8d34-115">See also</span></span>

- [<span data-ttu-id="b8d34-116">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b8d34-116">Metadata Interfaces</span></span>](metadata-interfaces.md)

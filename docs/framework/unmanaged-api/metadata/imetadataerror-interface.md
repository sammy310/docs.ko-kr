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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 277b93267f0537c8e499a8d8f3b456c4396a975c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966349"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="42eeb-102">IMetaDataError 인터페이스</span><span class="sxs-lookup"><span data-stu-id="42eeb-102">IMetaDataError Interface</span></span>
<span data-ttu-id="42eeb-103">메타 데이터 병합 중에 오류를 보고 하는 콜백 메커니즘을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="42eeb-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="42eeb-104">인터페이스 `IMetaDataError` 는 클라이언트에 의해 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42eeb-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="42eeb-105">메서드</span><span class="sxs-lookup"><span data-stu-id="42eeb-105">Methods</span></span>  
  
|<span data-ttu-id="42eeb-106">메서드</span><span class="sxs-lookup"><span data-stu-id="42eeb-106">Method</span></span>|<span data-ttu-id="42eeb-107">Description</span><span class="sxs-lookup"><span data-stu-id="42eeb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="42eeb-108">OnError 메서드</span><span class="sxs-lookup"><span data-stu-id="42eeb-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="42eeb-109">메타 데이터 병합 중에 발생 하는 오류에 대 한 알림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="42eeb-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="42eeb-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="42eeb-110">Requirements</span></span>  
 <span data-ttu-id="42eeb-111">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="42eeb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42eeb-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="42eeb-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="42eeb-113">**라이브러리** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42eeb-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="42eeb-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42eeb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42eeb-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="42eeb-115">See also</span></span>

- [<span data-ttu-id="42eeb-116">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="42eeb-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)

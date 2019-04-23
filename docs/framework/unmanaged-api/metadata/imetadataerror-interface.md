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
ms.openlocfilehash: 37f1f6055ec8fa68fe804780d2893d20c978e6bd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59188632"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="37a7c-102">IMetaDataError 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37a7c-102">IMetaDataError Interface</span></span>
<span data-ttu-id="37a7c-103">메타 데이터를 병합 하는 동안 오류를 보고 하는 콜백 메커니즘을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a7c-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37a7c-104">`IMetaDataError` 클라이언트에서 인터페이스를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a7c-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="37a7c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="37a7c-105">Methods</span></span>  
  
|<span data-ttu-id="37a7c-106">메서드</span><span class="sxs-lookup"><span data-stu-id="37a7c-106">Method</span></span>|<span data-ttu-id="37a7c-107">설명</span><span class="sxs-lookup"><span data-stu-id="37a7c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="37a7c-108">OnError 메서드</span><span class="sxs-lookup"><span data-stu-id="37a7c-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="37a7c-109">메타 데이터를 병합 하는 동안 발생 하는 오류에 대 한 알림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a7c-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="37a7c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="37a7c-110">Requirements</span></span>  
 <span data-ttu-id="37a7c-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="37a7c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37a7c-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="37a7c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="37a7c-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="37a7c-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="37a7c-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37a7c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37a7c-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="37a7c-115">See also</span></span>

- [<span data-ttu-id="37a7c-116">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37a7c-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)

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
ms.openlocfilehash: 44ecb73375f8a408fb0a38c3a2e2913f92ec4ca4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441624"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="d8b32-102">IMetaDataError 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8b32-102">IMetaDataError Interface</span></span>
<span data-ttu-id="d8b32-103">Provides a callback mechanism for reporting errors during the metadata merge.</span><span class="sxs-lookup"><span data-stu-id="d8b32-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d8b32-104">The `IMetaDataError` interface must be implemented by the client.</span><span class="sxs-lookup"><span data-stu-id="d8b32-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d8b32-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d8b32-105">Methods</span></span>  
  
|<span data-ttu-id="d8b32-106">메서드</span><span class="sxs-lookup"><span data-stu-id="d8b32-106">Method</span></span>|<span data-ttu-id="d8b32-107">설명</span><span class="sxs-lookup"><span data-stu-id="d8b32-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d8b32-108">OnError 메서드</span><span class="sxs-lookup"><span data-stu-id="d8b32-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="d8b32-109">Provides notification of errors that occur during the metadata merge.</span><span class="sxs-lookup"><span data-stu-id="d8b32-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d8b32-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d8b32-110">Requirements</span></span>  
 <span data-ttu-id="d8b32-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8b32-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8b32-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d8b32-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d8b32-113">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d8b32-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d8b32-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8b32-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8b32-115">참조</span><span class="sxs-lookup"><span data-stu-id="d8b32-115">See also</span></span>

- [<span data-ttu-id="d8b32-116">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8b32-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)

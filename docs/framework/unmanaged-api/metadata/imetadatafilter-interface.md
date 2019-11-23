---
title: IMetaDataFilter 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataFilter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter
helpviewer_keywords:
- IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type:
- apiref
ms.openlocfilehash: e8b15f478eb3b94b7cdcab3b69d54e7cc99be13b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440170"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="8ee73-102">IMetaDataFilter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ee73-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="8ee73-103">이미 수행된 반복 작업을 방지하려고 메타데이터 토큰을 표시 및 필터링하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee73-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8ee73-104">메서드</span><span class="sxs-lookup"><span data-stu-id="8ee73-104">Methods</span></span>  
  
|<span data-ttu-id="8ee73-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8ee73-105">Method</span></span>|<span data-ttu-id="8ee73-106">설명</span><span class="sxs-lookup"><span data-stu-id="8ee73-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8ee73-107">IsTokenMarked 메서드</span><span class="sxs-lookup"><span data-stu-id="8ee73-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="8ee73-108">Gets a value indicating whether the specified metadata token has been processed.</span><span class="sxs-lookup"><span data-stu-id="8ee73-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="8ee73-109">MarkToken 메서드</span><span class="sxs-lookup"><span data-stu-id="8ee73-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="8ee73-110">Sets a value indicating that the specified metadata token has been processed.</span><span class="sxs-lookup"><span data-stu-id="8ee73-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="8ee73-111">UnmarkAll 메서드</span><span class="sxs-lookup"><span data-stu-id="8ee73-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="8ee73-112">Removes the processing marks from all the tokens in the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="8ee73-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8ee73-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8ee73-113">Requirements</span></span>  
 <span data-ttu-id="8ee73-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ee73-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ee73-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8ee73-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8ee73-116">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8ee73-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8ee73-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ee73-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ee73-118">참조</span><span class="sxs-lookup"><span data-stu-id="8ee73-118">See also</span></span>

- [<span data-ttu-id="8ee73-119">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ee73-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)

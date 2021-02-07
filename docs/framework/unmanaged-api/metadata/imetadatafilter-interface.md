---
description: '자세히 알아보기: IMetaDataFilter 인터페이스'
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
ms.openlocfilehash: c994574207ccb26a5cb317e1673145a41f0d837d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677927"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="b53f1-103">IMetaDataFilter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b53f1-103">IMetaDataFilter Interface</span></span>

<span data-ttu-id="b53f1-104">이미 수행된 반복 작업을 방지하려고 메타데이터 토큰을 표시 및 필터링하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b53f1-104">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b53f1-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b53f1-105">Methods</span></span>  
  
|<span data-ttu-id="b53f1-106">메서드</span><span class="sxs-lookup"><span data-stu-id="b53f1-106">Method</span></span>|<span data-ttu-id="b53f1-107">설명</span><span class="sxs-lookup"><span data-stu-id="b53f1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b53f1-108">IsTokenMarked 메서드</span><span class="sxs-lookup"><span data-stu-id="b53f1-108">IsTokenMarked Method</span></span>](imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="b53f1-109">지정 된 메타 데이터 토큰이 처리 되었는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b53f1-109">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="b53f1-110">MarkToken 메서드</span><span class="sxs-lookup"><span data-stu-id="b53f1-110">MarkToken Method</span></span>](imetadatafilter-marktoken-method.md)|<span data-ttu-id="b53f1-111">지정 된 메타 데이터 토큰이 처리 되었음을 나타내는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b53f1-111">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="b53f1-112">UnmarkAll 메서드</span><span class="sxs-lookup"><span data-stu-id="b53f1-112">UnmarkAll Method</span></span>](imetadatafilter-unmarkall-method.md)|<span data-ttu-id="b53f1-113">현재 메타 데이터 범위에 있는 모든 토큰에서 처리 표시를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b53f1-113">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b53f1-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b53f1-114">Requirements</span></span>  

 <span data-ttu-id="b53f1-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b53f1-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b53f1-116">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="b53f1-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b53f1-117">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b53f1-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b53f1-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b53f1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b53f1-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b53f1-119">See also</span></span>

- [<span data-ttu-id="b53f1-120">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b53f1-120">Metadata Interfaces</span></span>](metadata-interfaces.md)

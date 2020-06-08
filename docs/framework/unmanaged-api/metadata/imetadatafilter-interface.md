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
ms.openlocfilehash: 821936d20a421739e8eb3d5df228888df7f022e3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503796"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="44e59-102">IMetaDataFilter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="44e59-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="44e59-103">이미 수행된 반복 작업을 방지하려고 메타데이터 토큰을 표시 및 필터링하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="44e59-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="44e59-104">메서드</span><span class="sxs-lookup"><span data-stu-id="44e59-104">Methods</span></span>  
  
|<span data-ttu-id="44e59-105">방법</span><span class="sxs-lookup"><span data-stu-id="44e59-105">Method</span></span>|<span data-ttu-id="44e59-106">설명</span><span class="sxs-lookup"><span data-stu-id="44e59-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="44e59-107">IsTokenMarked 메서드</span><span class="sxs-lookup"><span data-stu-id="44e59-107">IsTokenMarked Method</span></span>](imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="44e59-108">지정 된 메타 데이터 토큰이 처리 되었는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="44e59-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="44e59-109">MarkToken 메서드</span><span class="sxs-lookup"><span data-stu-id="44e59-109">MarkToken Method</span></span>](imetadatafilter-marktoken-method.md)|<span data-ttu-id="44e59-110">지정 된 메타 데이터 토큰이 처리 되었음을 나타내는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e59-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="44e59-111">UnmarkAll 메서드</span><span class="sxs-lookup"><span data-stu-id="44e59-111">UnmarkAll Method</span></span>](imetadatafilter-unmarkall-method.md)|<span data-ttu-id="44e59-112">현재 메타 데이터 범위에 있는 모든 토큰에서 처리 표시를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e59-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="44e59-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="44e59-113">Requirements</span></span>  
 <span data-ttu-id="44e59-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44e59-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44e59-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="44e59-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="44e59-116">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44e59-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="44e59-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44e59-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44e59-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44e59-118">See also</span></span>

- [<span data-ttu-id="44e59-119">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="44e59-119">Metadata Interfaces</span></span>](metadata-interfaces.md)

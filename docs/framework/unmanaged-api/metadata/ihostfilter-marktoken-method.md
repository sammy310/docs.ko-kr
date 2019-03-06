---
title: IHostFilter::MarkToken 메서드
ms.date: 03/30/2017
api_name:
- IHostFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 96f0b1648c8182b4d075a479f9bd376dbe33ef61
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487905"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="36698-102">IHostFilter::MarkToken 메서드</span><span class="sxs-lookup"><span data-stu-id="36698-102">IHostFilter::MarkToken Method</span></span>
<span data-ttu-id="36698-103">지정 된 메타 데이터 토큰을 처리할 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="36698-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36698-104">구문</span><span class="sxs-lookup"><span data-stu-id="36698-104">Syntax</span></span>  
  
```  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36698-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="36698-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="36698-106">[in] 처리할 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="36698-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36698-107">설명</span><span class="sxs-lookup"><span data-stu-id="36698-107">Remarks</span></span>  
 <span data-ttu-id="36698-108">일반적으로 토큰 메타 데이터 범위에 있을 경우 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36698-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="36698-109">합니다 `MarkToken` 메서드를 통해 메타 데이터 엔진에 전달 되는 [imetadataemit:: Sethandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="36698-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36698-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="36698-110">Requirements</span></span>  
 <span data-ttu-id="36698-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="36698-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36698-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="36698-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="36698-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="36698-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="36698-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36698-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36698-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="36698-115">See also</span></span>
- [<span data-ttu-id="36698-116">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="36698-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="36698-117">IHostFilter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="36698-117">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)

---
description: '자세히 알아보기: IHostFilter:: MarkToken 메서드'
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
ms.openlocfilehash: c8f5ecdef56b77e1b0031a93d6d8f7de79de4c3b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784186"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="8c511-103">IHostFilter::MarkToken 메서드</span><span class="sxs-lookup"><span data-stu-id="8c511-103">IHostFilter::MarkToken Method</span></span>

<span data-ttu-id="8c511-104">지정 된 메타 데이터 토큰이 처리 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8c511-104">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c511-105">구문</span><span class="sxs-lookup"><span data-stu-id="8c511-105">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c511-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8c511-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="8c511-107">진행 처리할 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8c511-107">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c511-108">설명</span><span class="sxs-lookup"><span data-stu-id="8c511-108">Remarks</span></span>  

 <span data-ttu-id="8c511-109">일반적으로 토큰은 메타 데이터 범위에 있는 경우 처리 하도록 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c511-109">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="8c511-110">`MarkToken`메서드는 [IMetaDataEmit:: SetHandler](imetadataemit-sethandler-method.md) 메서드를 통해 메타 데이터 엔진에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c511-110">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c511-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8c511-111">Requirements</span></span>  

 <span data-ttu-id="8c511-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c511-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c511-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="8c511-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8c511-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c511-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8c511-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c511-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c511-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c511-116">See also</span></span>

- [<span data-ttu-id="8c511-117">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8c511-117">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="8c511-118">IHostFilter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8c511-118">IHostFilter Interface</span></span>](ihostfilter-interface.md)

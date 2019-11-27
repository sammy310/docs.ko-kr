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
ms.openlocfilehash: 6f8df824ed36b7793d5f07e5b5cf51f65f9c8e24
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432232"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="f4d70-102">IHostFilter::MarkToken 메서드</span><span class="sxs-lookup"><span data-stu-id="f4d70-102">IHostFilter::MarkToken Method</span></span>
<span data-ttu-id="f4d70-103">지정 된 메타 데이터 토큰이 처리 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f4d70-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4d70-104">구문</span><span class="sxs-lookup"><span data-stu-id="f4d70-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4d70-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f4d70-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="f4d70-106">진행 처리할 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f4d70-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4d70-107">설명</span><span class="sxs-lookup"><span data-stu-id="f4d70-107">Remarks</span></span>  
 <span data-ttu-id="f4d70-108">일반적으로 토큰은 메타 데이터 범위에 있는 경우 처리 하도록 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d70-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="f4d70-109">`MarkToken` 메서드는 [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) 메서드를 통해 메타 데이터 엔진에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4d70-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4d70-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f4d70-110">Requirements</span></span>  
 <span data-ttu-id="f4d70-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4d70-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4d70-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="f4d70-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f4d70-113">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4d70-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f4d70-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4d70-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4d70-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="f4d70-115">See also</span></span>

- [<span data-ttu-id="f4d70-116">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f4d70-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="f4d70-117">IHostFilter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f4d70-117">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)

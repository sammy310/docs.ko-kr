---
title: IMetaDataError::OnError 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataError.OnError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError::OnError
helpviewer_keywords:
- IMetaDataError::OnError method [.NET Framework metadata]
- OnError method, IMetaDataError interface [.NET Framework metadata]
ms.assetid: c1e744b8-a6fb-4d9c-a971-8babc875d8f0
topic_type:
- apiref
ms.openlocfilehash: f10c55abcc044b5bbdbb940001a25f530a4688e4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431228"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="ba4d3-102">IMetaDataError::OnError 메서드</span><span class="sxs-lookup"><span data-stu-id="ba4d3-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="ba4d3-103">Provides notification of errors that occur during the metadata merge.</span><span class="sxs-lookup"><span data-stu-id="ba4d3-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba4d3-104">구문</span><span class="sxs-lookup"><span data-stu-id="ba4d3-104">Syntax</span></span>  
  
```cpp  
HRESULT OnError (  
    [in] HRESULT   hrError,   
    [in] mdToken   token  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba4d3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ba4d3-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="ba4d3-106">[in] The HRESULT error value returned to the calling method.</span><span class="sxs-lookup"><span data-stu-id="ba4d3-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="ba4d3-107">[in] The metadata token of the code object that was being merged when the error occurred.</span><span class="sxs-lookup"><span data-stu-id="ba4d3-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba4d3-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ba4d3-108">Requirements</span></span>  
 <span data-ttu-id="ba4d3-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba4d3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba4d3-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ba4d3-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ba4d3-111">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ba4d3-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ba4d3-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba4d3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba4d3-113">참조</span><span class="sxs-lookup"><span data-stu-id="ba4d3-113">See also</span></span>

- [<span data-ttu-id="ba4d3-114">IMetaDataError 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba4d3-114">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)

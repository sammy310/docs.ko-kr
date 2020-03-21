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
ms.openlocfilehash: 489fa217744e41ccb5d27d088790131c15e1ee52
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177393"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="a581b-102">IMetaDataError::OnError 메서드</span><span class="sxs-lookup"><span data-stu-id="a581b-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="a581b-103">메타데이터 병합 중에 발생하는 오류에 대한 알림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a581b-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a581b-104">구문</span><span class="sxs-lookup"><span data-stu-id="a581b-104">Syntax</span></span>  
  
```cpp  
HRESULT OnError (  
    [in] HRESULT   hrError,
    [in] mdToken   token  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a581b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a581b-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="a581b-106">【인】 호출 메서드에 반환 된 HRESULT 오류 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a581b-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="a581b-107">【인】 오류가 발생했을 때 병합중인 코드 개체의 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a581b-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a581b-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a581b-108">Requirements</span></span>  
 <span data-ttu-id="a581b-109">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a581b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a581b-110">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="a581b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a581b-111">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="a581b-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a581b-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a581b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a581b-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a581b-113">See also</span></span>

- [<span data-ttu-id="a581b-114">IMetaDataError 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a581b-114">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)

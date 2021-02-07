---
description: '자세히 알아보기: IMetaDataError:: OnError 메서드'
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
ms.openlocfilehash: 9556f1bd7758755d9160e3a2e91a1fe5786aa562
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670972"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="92294-103">IMetaDataError::OnError 메서드</span><span class="sxs-lookup"><span data-stu-id="92294-103">IMetaDataError::OnError Method</span></span>

<span data-ttu-id="92294-104">메타 데이터 병합 중에 발생 하는 오류에 대 한 알림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="92294-104">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92294-105">구문</span><span class="sxs-lookup"><span data-stu-id="92294-105">Syntax</span></span>  
  
```cpp  
HRESULT OnError (  
    [in] HRESULT   hrError,
    [in] mdToken   token  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92294-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="92294-106">Parameters</span></span>  

 `hrError`  
 <span data-ttu-id="92294-107">진행 호출 하는 메서드에 반환 되는 HRESULT 오류 값입니다.</span><span class="sxs-lookup"><span data-stu-id="92294-107">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="92294-108">진행 오류가 발생 했을 때 병합 되 고 있던 코드 개체의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="92294-108">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92294-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="92294-109">Requirements</span></span>  

 <span data-ttu-id="92294-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="92294-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92294-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="92294-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="92294-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92294-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="92294-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92294-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92294-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="92294-114">See also</span></span>

- [<span data-ttu-id="92294-115">IMetaDataError 인터페이스</span><span class="sxs-lookup"><span data-stu-id="92294-115">IMetaDataError Interface</span></span>](imetadataerror-interface.md)

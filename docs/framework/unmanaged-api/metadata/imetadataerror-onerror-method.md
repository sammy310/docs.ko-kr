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
ms.openlocfilehash: d2252f58af1a319d953fb320a99fad1cfec3dca0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492722"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="c4851-102">IMetaDataError::OnError 메서드</span><span class="sxs-lookup"><span data-stu-id="c4851-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="c4851-103">메타 데이터 병합 중에 발생 하는 오류에 대 한 알림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4851-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4851-104">구문</span><span class="sxs-lookup"><span data-stu-id="c4851-104">Syntax</span></span>  
  
```cpp  
HRESULT OnError (  
    [in] HRESULT   hrError,
    [in] mdToken   token  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4851-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c4851-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="c4851-106">진행 호출 하는 메서드에 반환 되는 HRESULT 오류 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c4851-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="c4851-107">진행 오류가 발생 했을 때 병합 되 고 있던 코드 개체의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c4851-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4851-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c4851-108">Requirements</span></span>  
 <span data-ttu-id="c4851-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c4851-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4851-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="c4851-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c4851-111">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4851-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c4851-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4851-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4851-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4851-113">See also</span></span>

- [<span data-ttu-id="c4851-114">IMetaDataError 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c4851-114">IMetaDataError Interface</span></span>](imetadataerror-interface.md)

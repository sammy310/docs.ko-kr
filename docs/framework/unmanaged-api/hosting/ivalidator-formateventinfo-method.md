---
title: IValidator::FormatEventInfo 메서드
ms.date: 03/30/2017
api_name:
- IValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FormatEventInfo
helpviewer_keywords:
- IValidator::FormatEventInfo method [.NET Framework hosting]
- FormatEventInfo method, IValidator interface [.NET Framework hosting]
ms.assetid: 4c0c7477-05ba-461b-b21b-cbfba95f1db1
topic_type:
- apiref
ms.openlocfilehash: 9b3a6bab8672f3ef3fca5f89c60b03a43477cce5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123305"
---
# <a name="ivalidatorformateventinfo-method"></a><span data-ttu-id="33fbf-102">IValidator::FormatEventInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="33fbf-102">IValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="33fbf-103">지정 된 유효성 검사 오류에 해당 하는 오류 메시지를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="33fbf-103">Gets the error message corresponding to the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33fbf-104">구문</span><span class="sxs-lookup"><span data-stu-id="33fbf-104">Syntax</span></span>  
  
```cpp  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33fbf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="33fbf-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="33fbf-106">진행 유효성 검사 오류 처리기에 전달 된 HRESULT 값입니다.</span><span class="sxs-lookup"><span data-stu-id="33fbf-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="33fbf-107">진행 유효성 검사 오류에 대 한 컨텍스트 정보를 포함 하는 `VEContext` 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="33fbf-107">[in] A `VEContext` instance that contains context information about the validation error.</span></span>  
  
 `msg`  
 <span data-ttu-id="33fbf-108">[in, out] 반환 된 오류 메시지를 포함 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="33fbf-108">[in, out] A string that contains the returned error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="33fbf-109">진행 오류 메시지의 최대 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="33fbf-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="33fbf-110">진행 오류를 설명 하는 추가 매개 변수가 포함 된 안전 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="33fbf-110">[in] A safe array that contains additional parameters describing the error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33fbf-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="33fbf-111">Requirements</span></span>  
 <span data-ttu-id="33fbf-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33fbf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33fbf-113">**헤더:** IValidator, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="33fbf-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="33fbf-114">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33fbf-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33fbf-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33fbf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  

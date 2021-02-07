---
description: '자세히 알아보기: IValidator:: FormatEventInfo 메서드'
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
ms.openlocfilehash: 28ecf9ab2b14cd2fdd178a4ad9d8e218f7038a9d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99680163"
---
# <a name="ivalidatorformateventinfo-method"></a><span data-ttu-id="4ed73-103">IValidator::FormatEventInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="4ed73-103">IValidator::FormatEventInfo Method</span></span>

<span data-ttu-id="4ed73-104">지정 된 유효성 검사 오류에 해당 하는 오류 메시지를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4ed73-104">Gets the error message corresponding to the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ed73-105">구문</span><span class="sxs-lookup"><span data-stu-id="4ed73-105">Syntax</span></span>  
  
```cpp  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ed73-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4ed73-106">Parameters</span></span>  

 `hVECode`  
 <span data-ttu-id="4ed73-107">진행 유효성 검사 오류 처리기에 전달 된 HRESULT 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed73-107">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="4ed73-108">진행 `VEContext` 유효성 검사 오류에 대 한 컨텍스트 정보를 포함 하는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed73-108">[in] A `VEContext` instance that contains context information about the validation error.</span></span>  
  
 `msg`  
 <span data-ttu-id="4ed73-109">[in, out] 반환 된 오류 메시지를 포함 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed73-109">[in, out] A string that contains the returned error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="4ed73-110">진행 오류 메시지의 최대 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed73-110">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="4ed73-111">진행 오류를 설명 하는 추가 매개 변수가 포함 된 안전 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed73-111">[in] A safe array that contains additional parameters describing the error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ed73-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4ed73-112">Requirements</span></span>  

 <span data-ttu-id="4ed73-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ed73-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ed73-114">**헤더:** IValidator, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="4ed73-114">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="4ed73-115">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ed73-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4ed73-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ed73-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  

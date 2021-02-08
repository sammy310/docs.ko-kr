---
description: '자세히 알아보기: GetRequestedRuntimeVersion 함수'
title: GetRequestedRuntimeVersion 함수
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersion
helpviewer_keywords:
- GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type:
- apiref
ms.openlocfilehash: 836cc4b875ddc427c6779950f5b68d2df8b6ef75
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785278"
---
# <a name="getrequestedruntimeversion-function"></a><span data-ttu-id="57f7c-103">GetRequestedRuntimeVersion 함수</span><span class="sxs-lookup"><span data-stu-id="57f7c-103">GetRequestedRuntimeVersion Function</span></span>

<span data-ttu-id="57f7c-104">지정 된 응용 프로그램에서 요청 하는 CLR (공용 언어 런타임)의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="57f7c-104">Gets the version number of the common language runtime (CLR) requested by the specified application.</span></span> <span data-ttu-id="57f7c-105">해당 버전이 설치 되지 않은 경우는 요청 된 버전 보다 먼저 설치 된 최신 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="57f7c-105">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 <span data-ttu-id="57f7c-106">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57f7c-106">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57f7c-107">구문</span><span class="sxs-lookup"><span data-stu-id="57f7c-107">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57f7c-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="57f7c-108">Parameters</span></span>  

 `pExe`  
 <span data-ttu-id="57f7c-109">진행 응용 프로그램의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="57f7c-109">[in] The name of the application.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="57f7c-110">제한이 성공적으로 완료 되 면 버전 번호 문자열을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="57f7c-110">[out] A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="57f7c-111">진행 버전 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="57f7c-111">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="57f7c-112">제한이 버전 번호 문자열의 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="57f7c-112">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57f7c-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="57f7c-113">Return Value</span></span>  

 <span data-ttu-id="57f7c-114">이 메서드는 Winerror.h에 정의 된 대로 다음 값 외에 표준 COM (구성 요소 개체 모델) 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="57f7c-114">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="57f7c-115">반환 코드</span><span class="sxs-lookup"><span data-stu-id="57f7c-115">Return code</span></span>|<span data-ttu-id="57f7c-116">설명</span><span class="sxs-lookup"><span data-stu-id="57f7c-116">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="57f7c-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="57f7c-117">S_OK</span></span>|<span data-ttu-id="57f7c-118">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="57f7c-118">The method completed successfully.</span></span>|  
|<span data-ttu-id="57f7c-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="57f7c-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="57f7c-120">버전 버퍼의 크기가 작아서 버전 문자열을 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57f7c-120">The version buffer is not large enough to store the version string.</span></span>|  
|<span data-ttu-id="57f7c-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="57f7c-121">E_POINTER</span></span>|<span data-ttu-id="57f7c-122">`pdwLength`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="57f7c-122">`pdwLength` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="57f7c-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="57f7c-123">Requirements</span></span>  

 <span data-ttu-id="57f7c-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57f7c-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57f7c-125">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="57f7c-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="57f7c-126">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="57f7c-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="57f7c-127">**.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57f7c-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57f7c-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="57f7c-128">See also</span></span>

- [<span data-ttu-id="57f7c-129">GetRequestedRuntimeInfo 함수</span><span class="sxs-lookup"><span data-stu-id="57f7c-129">GetRequestedRuntimeInfo Function</span></span>](getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="57f7c-130">GetVersionFromProcess 함수</span><span class="sxs-lookup"><span data-stu-id="57f7c-130">GetVersionFromProcess Function</span></span>](getversionfromprocess-function.md)
- [<span data-ttu-id="57f7c-131">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="57f7c-131">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)

---
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
ms.openlocfilehash: 6c16b02a5ae323ba80d44937f322810022dfa9f5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711639"
---
# <a name="getrequestedruntimeversion-function"></a><span data-ttu-id="8b357-102">GetRequestedRuntimeVersion 함수</span><span class="sxs-lookup"><span data-stu-id="8b357-102">GetRequestedRuntimeVersion Function</span></span>

<span data-ttu-id="8b357-103">지정 된 응용 프로그램에서 요청 하는 CLR (공용 언어 런타임)의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8b357-103">Gets the version number of the common language runtime (CLR) requested by the specified application.</span></span> <span data-ttu-id="8b357-104">해당 버전이 설치 되지 않은 경우는 요청 된 버전 보다 먼저 설치 된 최신 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8b357-104">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 <span data-ttu-id="8b357-105">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b357-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b357-106">구문</span><span class="sxs-lookup"><span data-stu-id="8b357-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b357-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8b357-107">Parameters</span></span>  

 `pExe`  
 <span data-ttu-id="8b357-108">진행 응용 프로그램의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8b357-108">[in] The name of the application.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="8b357-109">제한이 성공적으로 완료 되 면 버전 번호 문자열을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="8b357-109">[out] A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="8b357-110">진행 버전 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="8b357-110">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="8b357-111">제한이 버전 번호 문자열의 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8b357-111">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b357-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="8b357-112">Return Value</span></span>  

 <span data-ttu-id="8b357-113">이 메서드는 Winerror.h에 정의 된 대로 다음 값 외에 표준 COM (구성 요소 개체 모델) 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b357-113">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="8b357-114">반환 코드</span><span class="sxs-lookup"><span data-stu-id="8b357-114">Return code</span></span>|<span data-ttu-id="8b357-115">설명</span><span class="sxs-lookup"><span data-stu-id="8b357-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="8b357-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="8b357-116">S_OK</span></span>|<span data-ttu-id="8b357-117">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8b357-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="8b357-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="8b357-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="8b357-119">버전 버퍼의 크기가 작아서 버전 문자열을 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b357-119">The version buffer is not large enough to store the version string.</span></span>|  
|<span data-ttu-id="8b357-120">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="8b357-120">E_POINTER</span></span>|<span data-ttu-id="8b357-121">`pdwLength`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="8b357-121">`pdwLength` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8b357-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8b357-122">Requirements</span></span>  

 <span data-ttu-id="8b357-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b357-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b357-124">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8b357-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8b357-125">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8b357-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b357-126">**.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b357-126">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b357-127">참조</span><span class="sxs-lookup"><span data-stu-id="8b357-127">See also</span></span>

- [<span data-ttu-id="8b357-128">GetRequestedRuntimeInfo 함수</span><span class="sxs-lookup"><span data-stu-id="8b357-128">GetRequestedRuntimeInfo Function</span></span>](getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="8b357-129">GetVersionFromProcess 함수</span><span class="sxs-lookup"><span data-stu-id="8b357-129">GetVersionFromProcess Function</span></span>](getversionfromprocess-function.md)
- [<span data-ttu-id="8b357-130">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="8b357-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)

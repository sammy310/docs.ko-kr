---
title: GetCORVersion 함수
ms.date: 03/30/2017
api_name:
- GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORVersion
helpviewer_keywords:
- GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type:
- apiref
ms.openlocfilehash: 1283abaf6b08af1d842d8fe4469f7f6c15e38ec5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136429"
---
# <a name="getcorversion-function"></a><span data-ttu-id="eb3fb-102">GetCORVersion 함수</span><span class="sxs-lookup"><span data-stu-id="eb3fb-102">GetCORVersion Function</span></span>
<span data-ttu-id="eb3fb-103">현재 프로세스에서 실행 중인 CLR (공용 언어 런타임)의 버전 번호를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3fb-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="eb3fb-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb3fb-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb3fb-105">구문</span><span class="sxs-lookup"><span data-stu-id="eb3fb-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="eb3fb-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eb3fb-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="eb3fb-107">CLR이 프로세스에 현재 로드 된 런타임 버전을 지정 하는 문자열을 반환 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="eb3fb-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="eb3fb-108">반환 된 문자열은 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)에 전달 된 문자열과 동일한 형식을 사용 합니다 (예: "v 1.0.1216").</span><span class="sxs-lookup"><span data-stu-id="eb3fb-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="eb3fb-109">런타임이 아직 프로세스에 로드 되지 않은 경우이 함수는 컴퓨터에 설치 된 런타임의 최신 버전에 대 한 적절 한 디렉터리 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3fb-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="eb3fb-110">`pbuffer`에 보유할 수 있는 문자 (`WCHAR`s)의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="eb3fb-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="eb3fb-111">`pbuffer`에서 실제로 반환 된 문자 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="eb3fb-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="eb3fb-112">`pbuffer` null 포인터인 경우 런타임은 E_POINTER을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3fb-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="eb3fb-113">문자 수가 `pbuffer`의 길이 보다 큰 경우 런타임에서는 ERROR_INSUFFICIENT_BUFFER을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3fb-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb3fb-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eb3fb-114">Requirements</span></span>  
 <span data-ttu-id="eb3fb-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb3fb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb3fb-116">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="eb3fb-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eb3fb-117">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="eb3fb-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eb3fb-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb3fb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb3fb-119">참조</span><span class="sxs-lookup"><span data-stu-id="eb3fb-119">See also</span></span>

- [<span data-ttu-id="eb3fb-120">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="eb3fb-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

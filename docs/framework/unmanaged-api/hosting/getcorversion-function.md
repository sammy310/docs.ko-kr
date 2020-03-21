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
ms.openlocfilehash: 1f40f27651d2d75cf2c3e4d7d1c21e1f47d402af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178187"
---
# <a name="getcorversion-function"></a><span data-ttu-id="24036-102">GetCORVersion 함수</span><span class="sxs-lookup"><span data-stu-id="24036-102">GetCORVersion Function</span></span>
<span data-ttu-id="24036-103">현재 프로세스에서 실행 중인 공통 언어 런타임(CLR)의 버전 번호를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24036-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="24036-104">이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24036-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24036-105">구문</span><span class="sxs-lookup"><span data-stu-id="24036-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="24036-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="24036-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="24036-107">CLR이 현재 프로세스에 로드된 런타임 버전을 지정하는 문자열을 반환하는 버퍼에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="24036-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="24036-108">반환된 문자열은 [CorBindToRuntimeEx(예:](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)"v1.0.1216")에 전달된 문자열과 동일한 형식을 취합니다.</span><span class="sxs-lookup"><span data-stu-id="24036-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="24036-109">런타임이 아직 프로세스에 로드되지 않은 경우 함수는 컴퓨터에 설치된 최신 버전의 런타임에 대한 적절한 디렉터리 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24036-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="24036-110">에서 보유할`WCHAR`수 있는 문자 수입니다. `pbuffer`</span><span class="sxs-lookup"><span data-stu-id="24036-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="24036-111">실제로 반환된 문자 수에 `pbuffer`대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="24036-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="24036-112">null `pbuffer` 포인터인 경우 런타임은 E_POINTER 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24036-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="24036-113">문자 수가 클수록 `pbuffer` 길이가 ERROR_INSUFFICIENT_BUFFER 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="24036-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24036-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="24036-114">Requirements</span></span>  
 <span data-ttu-id="24036-115">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24036-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24036-116">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="24036-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="24036-117">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="24036-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="24036-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24036-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24036-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24036-119">See also</span></span>

- [<span data-ttu-id="24036-120">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="24036-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

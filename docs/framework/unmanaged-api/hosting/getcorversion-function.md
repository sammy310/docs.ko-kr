---
description: '자세한 정보: GetCORVersion 함수'
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
ms.openlocfilehash: 96899b2193be9307314dbc2afb7cd6d70d229cfe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785330"
---
# <a name="getcorversion-function"></a><span data-ttu-id="4eada-103">GetCORVersion 함수</span><span class="sxs-lookup"><span data-stu-id="4eada-103">GetCORVersion Function</span></span>

<span data-ttu-id="4eada-104">현재 프로세스에서 실행 중인 CLR (공용 언어 런타임)의 버전 번호를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eada-104">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="4eada-105">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4eada-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4eada-106">구문</span><span class="sxs-lookup"><span data-stu-id="4eada-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="4eada-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4eada-107">Parameters</span></span>  

 `pbuffer`  
 <span data-ttu-id="4eada-108">CLR이 프로세스에 현재 로드 된 런타임 버전을 지정 하는 문자열을 반환 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4eada-108">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="4eada-109">반환 된 문자열은 [CorBindToRuntimeEx](corbindtoruntimeex-function.md)에 전달 된 문자열과 동일한 형식을 사용 합니다 (예: "v 1.0.1216").</span><span class="sxs-lookup"><span data-stu-id="4eada-109">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="4eada-110">런타임이 아직 프로세스에 로드 되지 않은 경우이 함수는 컴퓨터에 설치 된 런타임의 최신 버전에 대 한 적절 한 디렉터리 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eada-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="4eada-111">에서 보유할 수 있는 문자 수입니다 `WCHAR` `pbuffer` .</span><span class="sxs-lookup"><span data-stu-id="4eada-111">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="4eada-112">에 실제로 반환 된 문자 수에 대 한 포인터 `pbuffer` 입니다.</span><span class="sxs-lookup"><span data-stu-id="4eada-112">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="4eada-113">`pbuffer`가 null 포인터인 경우 런타임은 E_POINTER을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eada-113">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="4eada-114">문자 수가의 길이 보다 큰 경우 `pbuffer` 런타임에서는 ERROR_INSUFFICIENT_BUFFER을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eada-114">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4eada-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4eada-115">Requirements</span></span>  

 <span data-ttu-id="4eada-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4eada-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4eada-117">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4eada-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4eada-118">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4eada-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4eada-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4eada-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eada-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4eada-120">See also</span></span>

- [<span data-ttu-id="4eada-121">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="4eada-121">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)

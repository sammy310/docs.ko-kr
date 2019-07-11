---
title: RunDll32ShimW 함수
ms.date: 03/30/2017
api_name:
- RunDll32ShimW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- RunDll32ShimW
helpviewer_keywords:
- RunDll32ShimW function [.NET Framework hosting]
ms.assetid: 9ea07b57-96e2-44df-8711-8fe6c119087f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 569efa9d14ef10d8c5cf735091778a6c78882815
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781159"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="bacba-102">RunDll32ShimW 함수</span><span class="sxs-lookup"><span data-stu-id="bacba-102">RunDll32ShimW Function</span></span>
<span data-ttu-id="bacba-103">지정된 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bacba-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="bacba-104">.NET Framework 4에서이 함수에 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bacba-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bacba-105">구문</span><span class="sxs-lookup"><span data-stu-id="bacba-105">Syntax</span></span>  
  
```cpp  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bacba-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bacba-106">Parameters</span></span>  
 `hwnd`  
 <span data-ttu-id="bacba-107">[in] 명령 출력은 표시 되는 창 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="bacba-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="bacba-108">[in] 명령이 포함 된 라이브러리에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="bacba-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="bacba-109">[in] 실행할 명령을 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="bacba-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="bacba-110">[in] 출력 창에 대 한 디스플레이 모드를 지정 하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="bacba-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bacba-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bacba-111">Requirements</span></span>  
 <span data-ttu-id="bacba-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bacba-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bacba-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bacba-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bacba-114">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bacba-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bacba-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bacba-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bacba-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="bacba-116">See also</span></span>

- [<span data-ttu-id="bacba-117">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="bacba-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

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
ms.openlocfilehash: ccfdf9ffab35f076b85c067c2b412020a5f541b2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765169"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="2d144-102">RunDll32ShimW 함수</span><span class="sxs-lookup"><span data-stu-id="2d144-102">RunDll32ShimW Function</span></span>
<span data-ttu-id="2d144-103">지정된 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2d144-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="2d144-104">이 함수에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="2d144-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d144-105">구문</span><span class="sxs-lookup"><span data-stu-id="2d144-105">Syntax</span></span>  
  
```  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d144-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2d144-106">Parameters</span></span>  
 `hwnd`  
 <span data-ttu-id="2d144-107">[in] 명령 출력은 표시 되는 창 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="2d144-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="2d144-108">[in] 명령이 포함 된 라이브러리에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="2d144-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="2d144-109">[in] 실행할 명령을 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2d144-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="2d144-110">[in] 출력 창에 대 한 디스플레이 모드를 지정 하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="2d144-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d144-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2d144-111">Requirements</span></span>  
 <span data-ttu-id="2d144-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2d144-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d144-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2d144-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2d144-114">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2d144-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d144-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d144-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d144-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="2d144-116">See also</span></span>

- [<span data-ttu-id="2d144-117">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="2d144-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

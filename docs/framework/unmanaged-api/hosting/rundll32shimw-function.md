---
description: '자세히 알아보기: RunDll32ShimW 함수'
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
ms.openlocfilehash: d01021358a6cddf15d1a0e1b223c9acff3c64ff7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679500"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="4538e-103">RunDll32ShimW 함수</span><span class="sxs-lookup"><span data-stu-id="4538e-103">RunDll32ShimW Function</span></span>

<span data-ttu-id="4538e-104">지정된 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4538e-104">Executes the specified command.</span></span>  
  
 <span data-ttu-id="4538e-105">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4538e-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4538e-106">구문</span><span class="sxs-lookup"><span data-stu-id="4538e-106">Syntax</span></span>  
  
```cpp  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4538e-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4538e-107">Parameters</span></span>  

 `hwnd`  
 <span data-ttu-id="4538e-108">진행 명령 출력이 표시 되는 창에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="4538e-108">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="4538e-109">진행 명령을 포함 하는 라이브러리에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="4538e-109">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="4538e-110">진행 실행할 명령을 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4538e-110">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="4538e-111">진행 출력 창에 대 한 디스플레이 모드를 지정 하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="4538e-111">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4538e-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4538e-112">Requirements</span></span>  

 <span data-ttu-id="4538e-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4538e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4538e-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4538e-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4538e-115">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4538e-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4538e-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4538e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4538e-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4538e-117">See also</span></span>

- [<span data-ttu-id="4538e-118">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="4538e-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)

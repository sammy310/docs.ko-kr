---
title: CorExitProcess 함수
ms.date: 03/30/2017
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
ms.openlocfilehash: 44578595b3cb790570c5359e714bd39c109cf1f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176463"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="f1f91-102">CorExitProcess 함수</span><span class="sxs-lookup"><span data-stu-id="f1f91-102">CorExitProcess Function</span></span>
<span data-ttu-id="f1f91-103">현재 관리되지 않는 프로세스를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="f1f91-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="f1f91-104">이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1f91-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="f1f91-105">대신 [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f1f91-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1f91-106">구문</span><span class="sxs-lookup"><span data-stu-id="f1f91-106">Syntax</span></span>  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1f91-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f1f91-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="f1f91-108">프로세스 종료 코드를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="f1f91-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1f91-109">설명</span><span class="sxs-lookup"><span data-stu-id="f1f91-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1f91-110">.NET Framework 4부터 `CorExitProcess` 시작하여 레거시 API가 바인딩된 런타임뿐만 아니라 프로세스의 모든 시작 런타임을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="f1f91-110">Beginning with the .NET Framework 4, `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1f91-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f1f91-111">Requirements</span></span>  
 <span data-ttu-id="f1f91-112">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1f91-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1f91-113">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="f1f91-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f1f91-114">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f1f91-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f1f91-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1f91-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1f91-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f1f91-116">See also</span></span>

- [<span data-ttu-id="f1f91-117">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="f1f91-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

---
title: GetCORSystemDirectory 함수
ms.date: 03/30/2017
api_name:
- GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORSystemDirectory
helpviewer_keywords:
- GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type:
- apiref
ms.openlocfilehash: 63fb505a92683fda21b6e71a6ca891ca35afba1d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136408"
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="29bc6-102">GetCORSystemDirectory 함수</span><span class="sxs-lookup"><span data-stu-id="29bc6-102">GetCORSystemDirectory Function</span></span>
<span data-ttu-id="29bc6-103">프로세스에 로드 된 CLR (공용 언어 런타임)의 설치 디렉터리를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="29bc6-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="29bc6-104">설치 디렉터리는 정규화 된 것입니다 (예: "c:\windows\microsoft.net\framework\v1.0.3705").</span><span class="sxs-lookup"><span data-stu-id="29bc6-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="29bc6-105">이 함수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29bc6-105">This function is deprecated.</span></span> <span data-ttu-id="29bc6-106">.NET Framework 4에서 제공 하는 [ICLRRuntimeInfo:: GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) 메서드로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29bc6-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) method provided in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29bc6-107">구문</span><span class="sxs-lookup"><span data-stu-id="29bc6-107">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="29bc6-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="29bc6-108">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="29bc6-109">제한이 런타임이 프로세스에 로드 되는 런타임에 대 한 설치 디렉터리의 정규화 된 이름을 포함 하는 문자열을 반환 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="29bc6-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="29bc6-110">런타임이 아직 프로세스에 로드 되지 않은 경우이 함수는 컴퓨터에 설치 된 런타임의 최신 버전에 대 한 적절 한 디렉터리 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="29bc6-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="29bc6-111">진행 `pbuffer`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="29bc6-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="29bc6-112">제한이 `pbuffer`에서 반환 되는 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="29bc6-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29bc6-113">주의</span><span class="sxs-lookup"><span data-stu-id="29bc6-113">Remarks</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="29bc6-114">CLR 버전 4를 실행 하는 프로세스에서는이 함수를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="29bc6-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="29bc6-115">이전 버전의 CLR이 컴퓨터에 설치 되어 있는 경우이 함수는 해당 버전의 설치 디렉터리를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="29bc6-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29bc6-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="29bc6-116">Requirements</span></span>  
 <span data-ttu-id="29bc6-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29bc6-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29bc6-118">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="29bc6-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="29bc6-119">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="29bc6-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29bc6-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29bc6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29bc6-121">참조</span><span class="sxs-lookup"><span data-stu-id="29bc6-121">See also</span></span>

- [<span data-ttu-id="29bc6-122">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="29bc6-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

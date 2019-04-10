---
title: ICLRRuntimeInfo::SetDefaultStartupFlags 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.SetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3174cf3b4f4f4ac4b2c8e69030357eb1e46cf3c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197830"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="99f23-102">ICLRRuntimeInfo::SetDefaultStartupFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="99f23-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="99f23-103">런타임을 시작 하는 데 사용할 호스트 구성 파일 및 시작 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f23-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="99f23-104">사용을 대체 하는이 메서드는 `startupFlags` 에서 매개 변수를 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 하 고 [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="99f23-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99f23-105">구문</span><span class="sxs-lookup"><span data-stu-id="99f23-105">Syntax</span></span>  
  
```  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99f23-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="99f23-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="99f23-107">[in] 호스트 시작 플래그 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="99f23-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="99f23-108">으로 동일한 플래그를 사용 합니다 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 하 고 [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) 함수.</span><span class="sxs-lookup"><span data-stu-id="99f23-108">Use the same flags as with the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="99f23-109">[in] 설정 하려면 호스트 구성 파일의 디렉터리 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="99f23-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99f23-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="99f23-110">Return Value</span></span>  
 <span data-ttu-id="99f23-111">이 메서드는 다음과 같은 특정 HRESULT를 반환 합니다. 메서드 오류를 나타내는 HRESULT 오류 뿐만 아니라 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f23-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="99f23-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="99f23-112">HRESULT</span></span>|<span data-ttu-id="99f23-113">설명</span><span class="sxs-lookup"><span data-stu-id="99f23-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="99f23-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="99f23-114">S_OK</span></span>|<span data-ttu-id="99f23-115">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="99f23-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99f23-116">설명</span><span class="sxs-lookup"><span data-stu-id="99f23-116">Remarks</span></span>  
 <span data-ttu-id="99f23-117">다중 스레드 호스트는이 메서드에 대 한 호출을 동기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f23-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="99f23-118">그렇지 않으면 스레드는 호출 될 수 있습니다는 `SetStartupFlags` 스레드 B에 대 한 호출을 완료 하는 메서드 `SetStartupFlags` 스레드 B는 런타임을 시작 하기 전에 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f23-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99f23-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="99f23-119">Requirements</span></span>  
 <span data-ttu-id="99f23-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="99f23-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99f23-121">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="99f23-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="99f23-122">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="99f23-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="99f23-123">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="99f23-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="99f23-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="99f23-124">See also</span></span>

- [<span data-ttu-id="99f23-125">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99f23-125">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="99f23-126">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99f23-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="99f23-127">호스팅</span><span class="sxs-lookup"><span data-stu-id="99f23-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

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
ms.openlocfilehash: aa02d42511a863434fef236f90afae2c5417a78d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504019"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="2414f-102">ICLRRuntimeInfo::SetDefaultStartupFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="2414f-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="2414f-103">런타임을 시작 하는 데 사용 되는 시작 플래그와 호스트 구성 파일을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2414f-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="2414f-104">이 메서드는 `startupFlags` [CorBindToRuntimeEx](corbindtoruntimeex-function.md) 및 [CorBindToRuntimeHost](corbindtoruntimehost-function.md) 함수에서 매개 변수의 사용을 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="2414f-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2414f-105">구문</span><span class="sxs-lookup"><span data-stu-id="2414f-105">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2414f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2414f-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="2414f-107">진행 설정할 호스트 시작 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="2414f-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="2414f-108">[CorBindToRuntimeEx](corbindtoruntimeex-function.md) 및 [CorBindToRuntimeHost](corbindtoruntimehost-function.md) 함수와 동일한 플래그를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2414f-108">Use the same flags as with the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="2414f-109">진행 설정할 호스트 구성 파일의 디렉터리 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2414f-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2414f-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="2414f-110">Return Value</span></span>  
 <span data-ttu-id="2414f-111">이 메서드는 다음과 같은 특정 HRESULT 및 메서드 오류를 나타내는 HRESULT 오류를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2414f-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2414f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2414f-112">HRESULT</span></span>|<span data-ttu-id="2414f-113">설명</span><span class="sxs-lookup"><span data-stu-id="2414f-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2414f-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="2414f-114">S_OK</span></span>|<span data-ttu-id="2414f-115">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2414f-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2414f-116">설명</span><span class="sxs-lookup"><span data-stu-id="2414f-116">Remarks</span></span>  
 <span data-ttu-id="2414f-117">다중 스레드 호스트는이 메서드에 대 한 호출을 동기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2414f-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="2414f-118">그렇지 않으면 스레드 `SetStartupFlags` b가에 대 한 호출을 완료 하 `SetStartupFlags` 고 스레드 b가 런타임을 시작 하기 전에 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2414f-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2414f-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2414f-119">Requirements</span></span>  
 <span data-ttu-id="2414f-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2414f-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2414f-121">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="2414f-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2414f-122">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2414f-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2414f-123">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2414f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2414f-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2414f-124">See also</span></span>

- [<span data-ttu-id="2414f-125">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2414f-125">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="2414f-126">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2414f-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="2414f-127">호스팅</span><span class="sxs-lookup"><span data-stu-id="2414f-127">Hosting</span></span>](index.md)

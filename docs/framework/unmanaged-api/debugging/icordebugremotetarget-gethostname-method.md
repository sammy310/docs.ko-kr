---
title: ICorDebugRemoteTarget::GetHostName 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget.GetHostName
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::GetHostName
helpviewer_keywords:
- ICorDebugRemoteTarget::GetHostName method [.NET Framework debugging]
- GetHostName method, ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: 1c7276f7-7e54-470c-808c-e13745ac07a1
topic_type:
- apiref
ms.openlocfilehash: 3e946d8a27ec6b568b2f3c3633695c9f6795c938
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712055"
---
# <a name="icordebugremotetargetgethostname-method"></a><span data-ttu-id="cac24-102">ICorDebugRemoteTarget::GetHostName 메서드</span><span class="sxs-lookup"><span data-stu-id="cac24-102">ICorDebugRemoteTarget::GetHostName Method</span></span>

<span data-ttu-id="cac24-103">정규화된 도메인 이름 또는 원격 디버깅 대상 컴퓨터의 IPv4 주소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cac24-103">Returns the fully qualified domain name or IPv4 address of the remote debugging target machine.</span></span> <span data-ttu-id="cac24-104">IPV6은 이번에 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cac24-104">IPV6 is not supported at this time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cac24-105">구문</span><span class="sxs-lookup"><span data-stu-id="cac24-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
## <a name="parameters"></a><span data-ttu-id="cac24-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cac24-106">Parameters</span></span>  

 `cchHostName`  
 <span data-ttu-id="cac24-107">진행 버퍼의 크기 (문자) `szHostName` 입니다.</span><span class="sxs-lookup"><span data-stu-id="cac24-107">[in] The size, in characters, of the `szHostName` buffer.</span></span> <span data-ttu-id="cac24-108">이 매개 변수가 0일 경우 `szHostName`은 null이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cac24-108">If this parameter is 0 (zero), `szHostName` must be null.</span></span>  
  
 `pcchHostName`  
 <span data-ttu-id="cac24-109">[out] 호스트 이름 또는 IP 주소의 null 종결자를 포함한 문자의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cac24-109">[out] The number of characters, including a null terminator, in the host name or IP address.</span></span> <span data-ttu-id="cac24-110">이 매개 변수는 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cac24-110">This parameter can be null.</span></span>  
  
 `szHostName`  
 <span data-ttu-id="cac24-111">[out] 호스트 이름 또는 IP 주소를 포함하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="cac24-111">[out] Buffer that contains the host name or IP address.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cac24-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="cac24-112">Return Value</span></span>  

 <span data-ttu-id="cac24-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="cac24-113">S_OK</span></span>  
 <span data-ttu-id="cac24-114">호스트 이름 또는 IP 주소가 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cac24-114">The host name or IP address was successfully returned.</span></span>  
  
 <span data-ttu-id="cac24-115">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="cac24-115">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="cac24-116">호스트 이름 또는 IP 주소를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cac24-116">Unable to return the host name or IP address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cac24-117">설명</span><span class="sxs-lookup"><span data-stu-id="cac24-117">Remarks</span></span>  

 <span data-ttu-id="cac24-118">이 메서드는 디버거 작성기에서 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="cac24-118">This method is implemented by the debugger writer.</span></span> <span data-ttu-id="cac24-119">다중 호출 패러다임을 따라야 합니다. 첫 번째 호출에서 호출자는 및 둘 다에 null을 `cchHostName` 전달 `szHostName` 하 고 `pcchHostName` 필요한 버퍼의 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cac24-119">It must follow the multiple call paradigm: On the first call, the caller passes null to both `cchHostName` and `szHostName`, and `pcchHostName` returns the size of the required buffer.</span></span> <span data-ttu-id="cac24-120">두 번째 호출에서 이전에 반환된 크기는 `cchHostName`에서 전달되고 적절한 크기의 버퍼는 `szHostName`에서 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="cac24-120">On the second call, the size that was previously returned is passed in `cchHostName`, and an appropriately sized buffer is passed in `szHostName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cac24-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cac24-121">Requirements</span></span>  

 <span data-ttu-id="cac24-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cac24-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cac24-123">**헤더:** CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="cac24-123">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="cac24-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cac24-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cac24-125">**.NET Framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="cac24-125">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cac24-126">참조</span><span class="sxs-lookup"><span data-stu-id="cac24-126">See also</span></span>

- [<span data-ttu-id="cac24-127">ICorDebugRemoteTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cac24-127">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="cac24-128">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cac24-128">ICorDebug Interface</span></span>](icordebug-interface.md)

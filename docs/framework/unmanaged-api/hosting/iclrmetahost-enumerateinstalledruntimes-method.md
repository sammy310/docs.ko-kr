---
title: ICLRMetaHost::EnumerateInstalledRuntimes 메서드
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateInstalledRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes
helpviewer_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes method [.NET Framework hosting]
- EnumerateInstalledRuntimes method [.NET Framework hosting]
ms.assetid: 9e359384-0d3d-451c-807e-5d7fcebf2be7
topic_type:
- apiref
ms.openlocfilehash: c99607bfe5fda01eb1abfd7771cb3907ddabeec5
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703781"
---
# <a name="iclrmetahostenumerateinstalledruntimes-method"></a><span data-ttu-id="657e0-102">ICLRMetaHost::EnumerateInstalledRuntimes 메서드</span><span class="sxs-lookup"><span data-stu-id="657e0-102">ICLRMetaHost::EnumerateInstalledRuntimes Method</span></span>
<span data-ttu-id="657e0-103">컴퓨터에 설치 된 CLR (공용 언어 런타임)의 각 버전에 대 한 유효한 [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 인터페이스를 포함 하는 열거형을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="657e0-103">Returns an enumeration that contains a valid [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface for each version of the common language runtime (CLR) that is installed on a computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="657e0-104">구문</span><span class="sxs-lookup"><span data-stu-id="657e0-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateInstalledRuntimes (  
    [out, retval] IEnumUnknown **ppEnumerator);  
```  
  
## <a name="parameters"></a><span data-ttu-id="657e0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="657e0-105">Parameters</span></span>  
 `ppEnumerator`  
 <span data-ttu-id="657e0-106">제한이 컴퓨터에 설치 된 각 CLR 버전에 해당 하는 [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 인터페이스의 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="657e0-106">[out] An enumeration of [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interfaces corresponding to each version of the CLR that is installed on the computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="657e0-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="657e0-107">Return Value</span></span>  
 <span data-ttu-id="657e0-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="657e0-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="657e0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="657e0-109">HRESULT</span></span>|<span data-ttu-id="657e0-110">설명</span><span class="sxs-lookup"><span data-stu-id="657e0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="657e0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="657e0-111">S_OK</span></span>|<span data-ttu-id="657e0-112">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="657e0-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="657e0-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="657e0-113">E_POINTER</span></span>|<span data-ttu-id="657e0-114">`ppEnumerator`가 null인 경우</span><span class="sxs-lookup"><span data-stu-id="657e0-114">`ppEnumerator` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="657e0-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="657e0-115">Requirements</span></span>  
 <span data-ttu-id="657e0-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="657e0-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="657e0-117">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="657e0-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="657e0-118">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="657e0-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="657e0-119">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="657e0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="657e0-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="657e0-120">See also</span></span>

- [<span data-ttu-id="657e0-121">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="657e0-121">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="657e0-122">호스팅</span><span class="sxs-lookup"><span data-stu-id="657e0-122">Hosting</span></span>](index.md)

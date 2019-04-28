---
title: ICorRuntimeHost::MapFile 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.MapFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::MapFile
helpviewer_keywords:
- ICorRuntimeHost::MapFile method [.NET Framework hosting]
- MapFile method [.NET Framework hosting]
ms.assetid: 45ae0502-0a31-4342-b7e3-f36e1cf738f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8a979e86dbe52577d0b58089015338e4a87750d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700178"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="4ef5a-102">ICorRuntimeHost::MapFile 메서드</span><span class="sxs-lookup"><span data-stu-id="4ef5a-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="4ef5a-103">지정된 된 파일을 메모리에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ef5a-103">Maps the specified file into memory.</span></span> <span data-ttu-id="4ef5a-104">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ef5a-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ef5a-105">구문</span><span class="sxs-lookup"><span data-stu-id="4ef5a-105">Syntax</span></span>  
  
```  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ef5a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4ef5a-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="4ef5a-107">[in] 매핑할 파일의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="4ef5a-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="4ef5a-108">[out] 매핑 파일을 시작 하는 시작 메모리 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="4ef5a-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ef5a-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4ef5a-109">Requirements</span></span>  
 <span data-ttu-id="4ef5a-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4ef5a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ef5a-111">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4ef5a-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4ef5a-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="4ef5a-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4ef5a-113">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="4ef5a-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ef5a-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="4ef5a-114">See also</span></span>

- [<span data-ttu-id="4ef5a-115">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ef5a-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)

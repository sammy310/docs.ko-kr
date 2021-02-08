---
description: '자세히 알아보기: ICorRuntimeHost:: 맵 파일 메서드'
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
ms.openlocfilehash: 80c01a036de83b32b9d0de745d76bb97825c980b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789634"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="ef2f4-103">ICorRuntimeHost::MapFile 메서드</span><span class="sxs-lookup"><span data-stu-id="ef2f4-103">ICorRuntimeHost::MapFile Method</span></span>

<span data-ttu-id="ef2f4-104">지정 된 파일을 메모리에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2f4-104">Maps the specified file into memory.</span></span> <span data-ttu-id="ef2f4-105">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef2f4-105">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef2f4-106">구문</span><span class="sxs-lookup"><span data-stu-id="ef2f4-106">Syntax</span></span>  
  
```cpp  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef2f4-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ef2f4-107">Parameters</span></span>  

 `hFile`  
 <span data-ttu-id="ef2f4-108">진행 매핑할 파일의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="ef2f4-108">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="ef2f4-109">제한이 파일 매핑을 시작할 시작 메모리 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ef2f4-109">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef2f4-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ef2f4-110">Requirements</span></span>  

 <span data-ttu-id="ef2f4-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ef2f4-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef2f4-112">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ef2f4-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ef2f4-113">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef2f4-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef2f4-114">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="ef2f4-114">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef2f4-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef2f4-115">See also</span></span>

- [<span data-ttu-id="ef2f4-116">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef2f4-116">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)

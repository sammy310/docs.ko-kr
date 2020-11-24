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
ms.openlocfilehash: 60e1d5d49f6f8c6fec060d8751e94410986aa3fd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671384"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="839d6-102">ICorRuntimeHost::MapFile 메서드</span><span class="sxs-lookup"><span data-stu-id="839d6-102">ICorRuntimeHost::MapFile Method</span></span>

<span data-ttu-id="839d6-103">지정 된 파일을 메모리에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="839d6-103">Maps the specified file into memory.</span></span> <span data-ttu-id="839d6-104">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="839d6-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="839d6-105">구문</span><span class="sxs-lookup"><span data-stu-id="839d6-105">Syntax</span></span>  
  
```cpp  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="839d6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="839d6-106">Parameters</span></span>  

 `hFile`  
 <span data-ttu-id="839d6-107">진행 매핑할 파일의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="839d6-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="839d6-108">제한이 파일 매핑을 시작할 시작 메모리 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="839d6-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="839d6-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="839d6-109">Requirements</span></span>  

 <span data-ttu-id="839d6-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="839d6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="839d6-111">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="839d6-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="839d6-112">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="839d6-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="839d6-113">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="839d6-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="839d6-114">참조</span><span class="sxs-lookup"><span data-stu-id="839d6-114">See also</span></span>

- [<span data-ttu-id="839d6-115">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="839d6-115">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)

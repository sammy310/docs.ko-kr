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
ms.openlocfilehash: bcf1b49f0576f5dbd73c001f8edff7a9ab29af22
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139509"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="c6509-102">ICorRuntimeHost::MapFile 메서드</span><span class="sxs-lookup"><span data-stu-id="c6509-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="c6509-103">지정 된 파일을 메모리에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="c6509-103">Maps the specified file into memory.</span></span> <span data-ttu-id="c6509-104">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6509-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6509-105">구문</span><span class="sxs-lookup"><span data-stu-id="c6509-105">Syntax</span></span>  
  
```cpp  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6509-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c6509-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="c6509-107">진행 매핑할 파일의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="c6509-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="c6509-108">제한이 파일 매핑을 시작할 시작 메모리 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c6509-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6509-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6509-109">Requirements</span></span>  
 <span data-ttu-id="c6509-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6509-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6509-111">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c6509-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6509-112">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6509-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6509-113">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="c6509-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6509-114">참조</span><span class="sxs-lookup"><span data-stu-id="c6509-114">See also</span></span>

- [<span data-ttu-id="c6509-115">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6509-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)

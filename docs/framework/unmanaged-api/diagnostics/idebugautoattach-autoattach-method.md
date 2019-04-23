---
title: IDebugAutoAttach::AutoAttach 메서드
ms.date: 03/30/2017
api_name:
- IDebugAutoAttach.AutoAttach
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IDebugAutoAttach::AutoAttach
helpviewer_keywords:
- AutoAttach method [.NET Framework debugging]
- IDebugAutoAttach::AutoAttach method [.NET Framework debugging]
ms.assetid: 3cf3bd9c-7d88-4afa-a476-94cdc7609aa6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5064e66708044d82e3a097c8235b5b28a3412200
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077136"
---
# <a name="idebugautoattachautoattach-method"></a><span data-ttu-id="28b72-102">IDebugAutoAttach::AutoAttach 메서드</span><span class="sxs-lookup"><span data-stu-id="28b72-102">IDebugAutoAttach::AutoAttach Method</span></span>
<span data-ttu-id="28b72-103">서버에서 호출한 디버거 자동 수행 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="28b72-103">Performs server-invoked debugger auto attach.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28b72-104">구문</span><span class="sxs-lookup"><span data-stu-id="28b72-104">Syntax</span></span>  
  
```  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28b72-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="28b72-105">Parameters</span></span>  
 `guidPort`  
 <span data-ttu-id="28b72-106">[in] 항상로 `GUID_NULL`합니다.</span><span class="sxs-lookup"><span data-stu-id="28b72-106">[in] Always set to `GUID_NULL`.</span></span>  
  
 `dwPid`  
 <span data-ttu-id="28b72-107">[in] 프로세스 ID, 일반적으로 사용 하 여 검색 된 `GetCurrentProcessId` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="28b72-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span></span>  
  
 `dwProgramType`  
 <span data-ttu-id="28b72-108">[in] 프로그램 형식: `AUTOATTACH_PROGRAM_WIN32`하십시오 `AUTOATTACH_PROGRAM_COMPLUS`, 또는 `AUTOATTACH_PROGRAM_UNKNOWN`합니다.</span><span class="sxs-lookup"><span data-stu-id="28b72-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span></span>  
  
 `dwProgramId`  
 <span data-ttu-id="28b72-109">[in] 프로그램 id입니다.</span><span class="sxs-lookup"><span data-stu-id="28b72-109">[in] Program ID.</span></span>  
  
 `pszSessionId`  
 <span data-ttu-id="28b72-110">[in] Debug 동사를 전달한 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="28b72-110">[in] String passed by the debug verb.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28b72-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="28b72-111">Return Value</span></span>  
 <span data-ttu-id="28b72-112">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="28b72-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28b72-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="28b72-113">Requirements</span></span>  
 <span data-ttu-id="28b72-114">**헤더:** DbgAutoAttach.h</span><span class="sxs-lookup"><span data-stu-id="28b72-114">**Header:** DbgAutoAttach.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28b72-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="28b72-115">See also</span></span>

- [<span data-ttu-id="28b72-116">IDebugAutoAttach 인터페이스</span><span class="sxs-lookup"><span data-stu-id="28b72-116">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)

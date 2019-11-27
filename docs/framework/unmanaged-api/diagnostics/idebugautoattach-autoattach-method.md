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
ms.openlocfilehash: 766aeb31436101babeab31b615a1c633578bfcc5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445529"
---
# <a name="idebugautoattachautoattach-method"></a><span data-ttu-id="8c6bf-102">IDebugAutoAttach::AutoAttach 메서드</span><span class="sxs-lookup"><span data-stu-id="8c6bf-102">IDebugAutoAttach::AutoAttach Method</span></span>
<span data-ttu-id="8c6bf-103">서버에서 호출 하는 디버거 자동 연결을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c6bf-103">Performs server-invoked debugger auto attach.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c6bf-104">구문</span><span class="sxs-lookup"><span data-stu-id="8c6bf-104">Syntax</span></span>  
  
```cpp  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c6bf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8c6bf-105">Parameters</span></span>  
 `guidPort`  
 <span data-ttu-id="8c6bf-106">진행 항상 `GUID_NULL`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c6bf-106">[in] Always set to `GUID_NULL`.</span></span>  
  
 `dwPid`  
 <span data-ttu-id="8c6bf-107">진행 일반적으로 `GetCurrentProcessId` 함수를 사용 하 여 검색 되는 프로세스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8c6bf-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span></span>  
  
 `dwProgramType`  
 <span data-ttu-id="8c6bf-108">진행 Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`또는 `AUTOATTACH_PROGRAM_UNKNOWN`합니다.</span><span class="sxs-lookup"><span data-stu-id="8c6bf-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span></span>  
  
 `dwProgramId`  
 <span data-ttu-id="8c6bf-109">진행 프로그램 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8c6bf-109">[in] Program ID.</span></span>  
  
 `pszSessionId`  
 <span data-ttu-id="8c6bf-110">진행 디버그 동사에 의해 전달 된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8c6bf-110">[in] String passed by the debug verb.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c6bf-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="8c6bf-111">Return Value</span></span>  
 <span data-ttu-id="8c6bf-112">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c6bf-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c6bf-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8c6bf-113">Requirements</span></span>  
 <span data-ttu-id="8c6bf-114">**헤더:** DbgAutoAttach</span><span class="sxs-lookup"><span data-stu-id="8c6bf-114">**Header:** DbgAutoAttach.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c6bf-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c6bf-115">See also</span></span>

- [<span data-ttu-id="8c6bf-116">IDebugAutoAttach 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8c6bf-116">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)

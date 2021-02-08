---
description: '자세히 알아보기: ICLRDataTarget:: GetMachineType 메서드'
title: ICLRDataTarget::GetMachineType 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetMachineType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetMachineType
helpviewer_keywords:
- ICLRDataTarget::GetMachineType method [.NET Framework debugging]
- GetMachineType method [.NET Framework debugging]
ms.assetid: 5f1f9c61-3e3b-48b2-b111-a4395f7623a7
topic_type:
- apiref
ms.openlocfilehash: 5624f734a77f51b4ea6cd9dd0c9df393c72e7d26
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801347"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="7d00d-103">ICLRDataTarget::GetMachineType 메서드</span><span class="sxs-lookup"><span data-stu-id="7d00d-103">ICLRDataTarget::GetMachineType Method</span></span>

<span data-ttu-id="7d00d-104">대상 프로세스에서 사용 하는 명령 집합의 종류에 대 한 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7d00d-104">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d00d-105">구문</span><span class="sxs-lookup"><span data-stu-id="7d00d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d00d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7d00d-106">Parameters</span></span>  

 `machineType`  
 <span data-ttu-id="7d00d-107">제한이 대상 프로세스에서 사용 하는 명령 집합을 나타내는 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7d00d-107">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="7d00d-108">반환 된는 `machineType` winnt.exe 헤더 파일에 정의 된 IMAGE_FILE_MACHINE 상수 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="7d00d-108">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d00d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d00d-109">Requirements</span></span>  

 <span data-ttu-id="7d00d-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d00d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d00d-111">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="7d00d-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="7d00d-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d00d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d00d-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d00d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d00d-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d00d-114">See also</span></span>

- [<span data-ttu-id="7d00d-115">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d00d-115">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)

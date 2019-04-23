---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff9c88d534e0bfe51075a76581af37aba791a3da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59148475"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="0a49d-102">ICLRDataTarget::GetMachineType 메서드</span><span class="sxs-lookup"><span data-stu-id="0a49d-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="0a49d-103">대상 프로세스에서 사용 되는 명령 집합의 종류에 대 한 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0a49d-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a49d-104">구문</span><span class="sxs-lookup"><span data-stu-id="0a49d-104">Syntax</span></span>  
  
```  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a49d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0a49d-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="0a49d-106">[out] 대상 프로세스는 명령 집합을 지정 하는 값에 대 한 포인터 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="0a49d-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="0a49d-107">반환 된 `machineType` WinNT.h 헤더 파일에 정의 된 IMAGE_FILE_MACHINE 상수 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="0a49d-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a49d-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a49d-108">Requirements</span></span>  
 <span data-ttu-id="0a49d-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0a49d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a49d-110">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="0a49d-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="0a49d-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a49d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a49d-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a49d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a49d-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="0a49d-113">See also</span></span>

- [<span data-ttu-id="0a49d-114">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a49d-114">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)

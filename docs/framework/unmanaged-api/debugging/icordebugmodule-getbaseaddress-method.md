---
description: '자세히 알아보기: ICorDebugModule:: GetBaseAddress 메서드'
title: ICorDebugModule::GetBaseAddress 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetBaseAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetBaseAddress
helpviewer_keywords:
- GetBaseAddress method [.NET Framework debugging]
- ICorDebugModule::GetBaseAddress method [.NET Framework debugging]
ms.assetid: 26a82815-1982-4eb7-92d1-5c3d318d5be4
topic_type:
- apiref
ms.openlocfilehash: bdfa4aeac3a9c06f666d56f1ee08ec503626ce7d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790817"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="bec46-103">ICorDebugModule::GetBaseAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="bec46-103">ICorDebugModule::GetBaseAddress Method</span></span>

<span data-ttu-id="bec46-104">모듈의 기본 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bec46-104">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bec46-105">구문</span><span class="sxs-lookup"><span data-stu-id="bec46-105">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bec46-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bec46-106">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="bec46-107">제한이 `CORDB_ADDRESS` 모듈의 기준 주소를 지정 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="bec46-107">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bec46-108">설명</span><span class="sxs-lookup"><span data-stu-id="bec46-108">Remarks</span></span>  

 <span data-ttu-id="bec46-109">모듈이 네이티브 이미지 (즉, 모듈이 네이티브 이미지 생성기, NGen.exe)에 의해 생성 된 경우 기본 주소는 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec46-109">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bec46-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bec46-110">Requirements</span></span>  

 <span data-ttu-id="bec46-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bec46-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bec46-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bec46-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bec46-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bec46-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bec46-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bec46-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bec46-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bec46-115">See also</span></span>

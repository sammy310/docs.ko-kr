---
title: ICorDebugAppDomain::GetModuleFromMetaDataInterface 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetModuleFromMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetModuleFromMetaDataInterface
helpviewer_keywords:
- ICorDebugAppDomain::GetModuleFromMetaDatainterface method [.NET Framework debugging]
- GetModuleFromMetaDatainterface method [.NET Framework debugging]
ms.assetid: f35225b3-5dda-4d5a-913d-b3373e9ab81e
topic_type:
- apiref
ms.openlocfilehash: f317eb1b3d91fc005d59d6a06bad329a5f68aa11
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895222"
---
# <a name="icordebugappdomaingetmodulefrommetadatainterface-method"></a><span data-ttu-id="5cea4-102">ICorDebugAppDomain::GetModuleFromMetaDataInterface 메서드</span><span class="sxs-lookup"><span data-stu-id="5cea4-102">ICorDebugAppDomain::GetModuleFromMetaDataInterface Method</span></span>
<span data-ttu-id="5cea4-103">지정 된 메타 데이터 인터페이스에 해당 하는 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5cea4-103">Gets the module that corresponds to the given metadata interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cea4-104">구문</span><span class="sxs-lookup"><span data-stu-id="5cea4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleFromMetaDataInterface (  
    [in] IUnknown           *pIMetaData,  
    [out] ICorDebugModule  **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cea4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5cea4-105">Parameters</span></span>  
 `pIMetaData`  
 <span data-ttu-id="5cea4-106">진행 [메타 데이터 인터페이스](../metadata/metadata-interfaces.md)중 하나인 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5cea4-106">[in] A pointer to an object that is one of the [Metadata interfaces](../metadata/metadata-interfaces.md).</span></span>  
  
 `ppModule`  
 <span data-ttu-id="5cea4-107">제한이 지정 된 메타 데이터 인터페이스에 해당 하는 모듈을 나타내는 ICorDebugModule 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5cea4-107">[out] A pointer to the address of an ICorDebugModule object that represents the module corresponding to the given metadata interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cea4-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5cea4-108">Requirements</span></span>  
 <span data-ttu-id="5cea4-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5cea4-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cea4-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5cea4-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5cea4-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5cea4-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5cea4-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cea4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

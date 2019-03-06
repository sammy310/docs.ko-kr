---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 메서드
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24560ed4b0bb7ca04d5859280baa594fbb2e4097
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473471"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="9e80e-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="9e80e-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="9e80e-103">비동기 작업을 시작 하는 시작 메서드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e80e-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e80e-104">구문</span><span class="sxs-lookup"><span data-stu-id="9e80e-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e80e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9e80e-105">Parameters</span></span>  
  
|<span data-ttu-id="9e80e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9e80e-106">Parameter</span></span>|<span data-ttu-id="9e80e-107">설명</span><span class="sxs-lookup"><span data-stu-id="9e80e-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="9e80e-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="9e80e-108">Return Value</span></span>  
 <span data-ttu-id="9e80e-109">`HRESULT`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9e80e-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e80e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9e80e-110">Requirements</span></span>  
 <span data-ttu-id="9e80e-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9e80e-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e80e-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="9e80e-112">See also</span></span>
- [<span data-ttu-id="9e80e-113">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9e80e-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)

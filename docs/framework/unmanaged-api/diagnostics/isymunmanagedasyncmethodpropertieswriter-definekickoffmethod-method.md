---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 메서드
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: ccf1287a1b0218e7f2560e1afbb0930c93b43263
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129166"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="94bc8-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="94bc8-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="94bc8-103">비동기 작업을 시작 하는 시작 메서드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94bc8-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94bc8-104">구문</span><span class="sxs-lookup"><span data-stu-id="94bc8-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94bc8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="94bc8-105">Parameters</span></span>  
  
|<span data-ttu-id="94bc8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="94bc8-106">Parameter</span></span>|<span data-ttu-id="94bc8-107">설명</span><span class="sxs-lookup"><span data-stu-id="94bc8-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="94bc8-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="94bc8-108">Return Value</span></span>  
 <span data-ttu-id="94bc8-109">`HRESULT`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="94bc8-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94bc8-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="94bc8-110">Requirements</span></span>  
 <span data-ttu-id="94bc8-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="94bc8-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94bc8-112">참조</span><span class="sxs-lookup"><span data-stu-id="94bc8-112">See also</span></span>

- [<span data-ttu-id="94bc8-113">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="94bc8-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)

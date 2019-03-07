---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 메서드
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bac541909e07aadff06006fba8c3cfcf4dc5465
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486227"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="f5035-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="f5035-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="f5035-103">비동기의 그룹을 정의 현재 메서드에 대 한 작업을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="f5035-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="f5035-104">각 yield 오프셋 일치는 await 반환 명령, 잠재적인 yield 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5035-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="f5035-105">각 `breakpointMethod` / `breakpointOffset` 쌍 알려줍니다 있는 비동기 작업을 다시 시작 됩니다는 다른 방법을에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5035-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5035-106">구문</span><span class="sxs-lookup"><span data-stu-id="f5035-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5035-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f5035-107">Parameters</span></span>  
  
|<span data-ttu-id="f5035-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f5035-108">Parameter</span></span>|<span data-ttu-id="f5035-109">설명</span><span class="sxs-lookup"><span data-stu-id="f5035-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="f5035-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="f5035-110">Return Value</span></span>  
 <span data-ttu-id="f5035-111">`HRESULT`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f5035-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5035-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f5035-112">Requirements</span></span>  
 <span data-ttu-id="f5035-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f5035-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5035-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="f5035-114">See also</span></span>
- [<span data-ttu-id="f5035-115">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5035-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)

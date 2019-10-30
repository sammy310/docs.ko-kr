---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 메서드
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
ms.openlocfilehash: 59e3a95a4d2573263600da60b4f852caa361138e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129193"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="1c831-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="1c831-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="1c831-103">현재 메서드에서 비동기 대기 작업 그룹을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c831-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="1c831-104">각 양보 오프셋은 대기의 반환 명령과 일치 하므로 잠재적 양보를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c831-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="1c831-105">각 `breakpointMethod`/`breakpointOffset` 쌍은 다른 메서드에 있을 수 있는 비동기 작업을 다시 시작할 위치를 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c831-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c831-106">구문</span><span class="sxs-lookup"><span data-stu-id="1c831-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c831-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1c831-107">Parameters</span></span>  
  
|<span data-ttu-id="1c831-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1c831-108">Parameter</span></span>|<span data-ttu-id="1c831-109">설명</span><span class="sxs-lookup"><span data-stu-id="1c831-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="1c831-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="1c831-110">Return Value</span></span>  
 <span data-ttu-id="1c831-111">`HRESULT`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1c831-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c831-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1c831-112">Requirements</span></span>  
 <span data-ttu-id="1c831-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="1c831-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c831-114">참조</span><span class="sxs-lookup"><span data-stu-id="1c831-114">See also</span></span>

- [<span data-ttu-id="1c831-115">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c831-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)

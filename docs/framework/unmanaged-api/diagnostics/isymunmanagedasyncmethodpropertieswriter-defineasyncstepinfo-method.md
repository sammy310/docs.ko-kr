---
description: ISymUnmanagedAsyncMethodPropertiesWriter::D efineAsyncStepInfo 메서드에 대해 자세히 알아보세요.
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 메서드
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
ms.openlocfilehash: f95436b10041ae5bfd56ca080a9b8ce70748022c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790245"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="d2043-103">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="d2043-103">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>

<span data-ttu-id="d2043-104">현재 메서드에서 비동기 대기 작업 그룹을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2043-104">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="d2043-105">각 양보 오프셋은 대기의 반환 명령과 일치 하므로 잠재적 양보를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2043-105">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="d2043-106">각 `breakpointMethod` / `breakpointOffset` 쌍은 다른 메서드에 있을 수 있는 비동기 작업을 다시 시작할 위치를 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d2043-106">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2043-107">구문</span><span class="sxs-lookup"><span data-stu-id="d2043-107">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2043-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d2043-108">Parameters</span></span>  
  
|<span data-ttu-id="d2043-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d2043-109">Parameter</span></span>|<span data-ttu-id="d2043-110">설명</span><span class="sxs-lookup"><span data-stu-id="d2043-110">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="d2043-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="d2043-111">Return Value</span></span>  

 <span data-ttu-id="d2043-112">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d2043-112">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2043-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d2043-113">Requirements</span></span>  

 <span data-ttu-id="d2043-114">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="d2043-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2043-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2043-115">See also</span></span>

- [<span data-ttu-id="d2043-116">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2043-116">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)

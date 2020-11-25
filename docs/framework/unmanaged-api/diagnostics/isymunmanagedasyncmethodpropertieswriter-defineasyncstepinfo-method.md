---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 메서드
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
ms.openlocfilehash: f8c77e44183fd92704aa91ca1cfd7e3fa68aa27f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719621"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="ffb16-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="ffb16-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>

<span data-ttu-id="ffb16-103">현재 메서드에서 비동기 대기 작업 그룹을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb16-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="ffb16-104">각 양보 오프셋은 대기의 반환 명령과 일치 하므로 잠재적 양보를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb16-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="ffb16-105">각 `breakpointMethod` / `breakpointOffset` 쌍은 다른 메서드에 있을 수 있는 비동기 작업을 다시 시작할 위치를 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ffb16-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffb16-106">구문</span><span class="sxs-lookup"><span data-stu-id="ffb16-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffb16-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ffb16-107">Parameters</span></span>  
  
|<span data-ttu-id="ffb16-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ffb16-108">Parameter</span></span>|<span data-ttu-id="ffb16-109">설명</span><span class="sxs-lookup"><span data-stu-id="ffb16-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="ffb16-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="ffb16-110">Return Value</span></span>  

 <span data-ttu-id="ffb16-111">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb16-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffb16-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ffb16-112">Requirements</span></span>  

 <span data-ttu-id="ffb16-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="ffb16-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffb16-114">참조</span><span class="sxs-lookup"><span data-stu-id="ffb16-114">See also</span></span>

- [<span data-ttu-id="ffb16-115">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ffb16-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)

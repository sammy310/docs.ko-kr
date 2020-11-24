---
title: ISymUnmanagedWriter4::GetDebugInfoWithPadding 메서드
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
ms.openlocfilehash: 4ac2cccfb17d82d8c62ad7db89161aa794825ae5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678279"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="3e8ec-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding 메서드</span><span class="sxs-lookup"><span data-stu-id="3e8ec-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>

<span data-ttu-id="3e8ec-103">는 [GetDebugInfo 메서드와](isymunmanagedwriter-getdebuginfo-method.md) 동일 하 게 작동 합니다. 단, 경로 문자열은 종료 null 문자 다음에 0으로 채워져 문자열 데이터의 고정 크기를 만듭니다 `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="3e8ec-103">Functions the same as [GetDebugInfo Method](isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="3e8ec-104">패딩은 경로 문자열 길이 자체가 보다 작은 경우에만 지정 됩니다 `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="3e8ec-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="3e8ec-105">따라서 PE 파일의 차이점을 쉽게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e8ec-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e8ec-106">구문</span><span class="sxs-lookup"><span data-stu-id="3e8ec-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e8ec-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3e8ec-107">Parameters</span></span>  
  
|<span data-ttu-id="3e8ec-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3e8ec-108">Parameter</span></span>|<span data-ttu-id="3e8ec-109">설명</span><span class="sxs-lookup"><span data-stu-id="3e8ec-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="3e8ec-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="3e8ec-110">Return Value</span></span>  

 <span data-ttu-id="3e8ec-111">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3e8ec-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e8ec-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e8ec-112">Requirements</span></span>  

 <span data-ttu-id="3e8ec-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="3e8ec-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e8ec-114">참조</span><span class="sxs-lookup"><span data-stu-id="3e8ec-114">See also</span></span>

- [<span data-ttu-id="3e8ec-115">ISymUnmanagedWriter4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3e8ec-115">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)

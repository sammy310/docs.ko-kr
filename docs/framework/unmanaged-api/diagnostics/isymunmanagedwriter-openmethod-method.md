---
title: ISymUnmanagedWriter::OpenMethod 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenMethod
helpviewer_keywords:
- ISymUnmanagedWriter::OpenMethod method [.NET Framework debugging]
- OpenMethod method [.NET Framework debugging]
ms.assetid: fb90cb7f-af88-45e8-a99f-80a0bbddb08b
topic_type:
- apiref
ms.openlocfilehash: deb3a28ffb73754b4c03496a6a72325418f1a4fc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722910"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="0f035-102">ISymUnmanagedWriter::OpenMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="0f035-102">ISymUnmanagedWriter::OpenMethod Method</span></span>

<span data-ttu-id="0f035-103">기호 정보를 내보내는 메서드를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0f035-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="0f035-104">지정 된 메서드는 시퀀스 위치, 매개 변수 및 어휘 범위를 정의 하는 호출에 대 한 현재 메서드가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f035-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="0f035-105">전체 메서드 주위에는 암시적 어휘 범위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f035-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="0f035-106">이전에 닫힌 메서드를 다시 열면 해당 메서드에 대해 이전에 정의 된 기호가 모두 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="0f035-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="0f035-107">한 번에 하나의 개방형 메서드만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f035-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f035-108">구문</span><span class="sxs-lookup"><span data-stu-id="0f035-108">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f035-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0f035-109">Parameters</span></span>  

 `method`  
 <span data-ttu-id="0f035-110">진행 열려는 메서드의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0f035-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f035-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="0f035-111">Return Value</span></span>  

 <span data-ttu-id="0f035-112">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="0f035-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f035-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f035-113">Requirements</span></span>  

 <span data-ttu-id="0f035-114">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="0f035-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f035-115">참조</span><span class="sxs-lookup"><span data-stu-id="0f035-115">See also</span></span>

- [<span data-ttu-id="0f035-116">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f035-116">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="0f035-117">CloseMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="0f035-117">CloseMethod Method</span></span>](isymunmanagedwriter-closemethod-method.md)
- [<span data-ttu-id="0f035-118">OpenMethod2 메서드</span><span class="sxs-lookup"><span data-stu-id="0f035-118">OpenMethod2 Method</span></span>](isymunmanagedwriter3-openmethod2-method.md)

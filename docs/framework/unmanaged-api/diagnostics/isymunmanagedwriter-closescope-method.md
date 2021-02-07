---
description: '자세히 알아보기: ISymUnmanagedWriter:: CloseScope 메서드'
title: ISymUnmanagedWriter::CloseScope 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type:
- apiref
ms.openlocfilehash: bb41e69955632d1e4d86250a63a9f25a7d1ae807
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762554"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="0cbfc-103">ISymUnmanagedWriter::CloseScope 메서드</span><span class="sxs-lookup"><span data-stu-id="0cbfc-103">ISymUnmanagedWriter::CloseScope Method</span></span>

<span data-ttu-id="0cbfc-104">현재 어휘 범위를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="0cbfc-104">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cbfc-105">구문</span><span class="sxs-lookup"><span data-stu-id="0cbfc-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0cbfc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0cbfc-106">Parameters</span></span>  

 `endOffset`  
 <span data-ttu-id="0cbfc-107">진행 어휘 범위에서 마지막 명령의 끝에 있는 지점에서의 오프셋 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="0cbfc-107">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0cbfc-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="0cbfc-108">Return Value</span></span>  

 <span data-ttu-id="0cbfc-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="0cbfc-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0cbfc-110">설명</span><span class="sxs-lookup"><span data-stu-id="0cbfc-110">Remarks</span></span>  

 <span data-ttu-id="0cbfc-111">범위가 닫히면 변수 내에서 더 이상 변수를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0cbfc-111">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="0cbfc-112">[ISymUnmanagedWriter:: OpenScope](isymunmanagedwriter-openscope-method.md) 는 나중에 범위의 시작 및 끝 오프셋을 정의 하는 [ISymUnmanagedWriter:: SetScopeRange](isymunmanagedwriter-setscoperange-method.md) 와 함께 사용할 수 있는 불투명 범위 식별자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cbfc-112">[ISymUnmanagedWriter::OpenScope](isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="0cbfc-113">이 경우 `ISymUnmanagedWriter::OpenScope` 및 `ISymUnmanagedWriter::CloseScope`에 전달된 오프셋은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cbfc-113">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="0cbfc-114">범위 식별자는 현재 메서드에서만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cbfc-114">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cbfc-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0cbfc-115">Requirements</span></span>  

 <span data-ttu-id="0cbfc-116">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="0cbfc-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cbfc-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0cbfc-117">See also</span></span>

- [<span data-ttu-id="0cbfc-118">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0cbfc-118">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)

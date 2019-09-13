---
title: ISymUnmanagedWriter::SetSymAttribute 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetSymAttribute
helpviewer_keywords:
- SetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedWriter::SetSymAttribute method [.NET Framework debugging]
ms.assetid: 64d9b80e-b883-4539-89c7-03573185a1eb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4450c262b75a73114cb7de7de98567f053bbf564
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894468"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="644f7-102">ISymUnmanagedWriter::SetSymAttribute 메서드</span><span class="sxs-lookup"><span data-stu-id="644f7-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="644f7-103">이름에 따라 사용자 지정 특성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="644f7-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="644f7-104">이러한 특성은 메타 데이터 사용자 지정 특성과 달리 기호 저장소에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="644f7-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="644f7-105">구문</span><span class="sxs-lookup"><span data-stu-id="644f7-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="644f7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="644f7-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="644f7-107">진행 특성이 정의 되는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="644f7-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="644f7-108">진행 특성 이름을 포함 `WCHAR` 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="644f7-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="644f7-109">진행 배열의크기`data` 를 나타내는입니다. `ULONG32`</span><span class="sxs-lookup"><span data-stu-id="644f7-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="644f7-110">진행 특성 값입니다.</span><span class="sxs-lookup"><span data-stu-id="644f7-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="644f7-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="644f7-111">Return Value</span></span>  
 <span data-ttu-id="644f7-112">메서드가 성공 하면 S_OK이 고, 그렇지 않으면입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="644f7-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="644f7-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="644f7-113">Requirements</span></span>  
 <span data-ttu-id="644f7-114">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="644f7-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="644f7-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="644f7-115">See also</span></span>

- [<span data-ttu-id="644f7-116">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="644f7-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

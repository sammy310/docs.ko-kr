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
ms.openlocfilehash: 8a4d205586921b377147eeab80754e1a0d9e52b0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427848"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="828a2-102">ISymUnmanagedWriter::SetSymAttribute 메서드</span><span class="sxs-lookup"><span data-stu-id="828a2-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="828a2-103">이름에 따라 사용자 지정 특성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="828a2-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="828a2-104">이러한 특성은 메타 데이터 사용자 지정 특성과 달리 기호 저장소에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="828a2-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="828a2-105">구문</span><span class="sxs-lookup"><span data-stu-id="828a2-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="828a2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="828a2-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="828a2-107">진행 특성이 정의 되는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="828a2-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="828a2-108">진행 특성 이름을 포함 하는 `WCHAR`에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="828a2-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="828a2-109">진행 `data` 배열의 크기를 나타내는 `ULONG32`입니다.</span><span class="sxs-lookup"><span data-stu-id="828a2-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="828a2-110">진행 특성 값입니다.</span><span class="sxs-lookup"><span data-stu-id="828a2-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="828a2-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="828a2-111">Return Value</span></span>  
 <span data-ttu-id="828a2-112">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="828a2-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="828a2-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="828a2-113">Requirements</span></span>  
 <span data-ttu-id="828a2-114">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="828a2-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="828a2-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="828a2-115">See also</span></span>

- [<span data-ttu-id="828a2-116">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="828a2-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

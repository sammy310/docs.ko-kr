---
description: ISymUnmanagedWriter::D efineField 메서드에 대해 자세히 알아보세요.
title: ISymUnmanagedWriter::DefineField 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineField
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineField
helpviewer_keywords:
- ISymUnmanagedWriter::DefineField method [.NET Framework debugging]
- DefineField method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: c6a1f797-dbf4-40f5-ab99-d9b4bfb26148
topic_type:
- apiref
ms.openlocfilehash: f5bb47d4691780d94baf50cc9ceb3c14b1fa16ec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762398"
---
# <a name="isymunmanagedwriterdefinefield-method"></a><span data-ttu-id="ff553-103">ISymUnmanagedWriter::DefineField 메서드</span><span class="sxs-lookup"><span data-stu-id="ff553-103">ISymUnmanagedWriter::DefineField Method</span></span>

<span data-ttu-id="ff553-104">메서드 내에 없는 단일 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff553-104">Defines a single variable that is not within a method.</span></span> <span data-ttu-id="ff553-105">이 메서드는 클래스, 비트 필드 등의 특정 필드에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff553-105">This method is used for certain fields in classes, bit fields, and so on.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff553-106">구문</span><span class="sxs-lookup"><span data-stu-id="ff553-106">Syntax</span></span>  
  
```cpp  
HRESULT DefineField(  
    [in] mdTypeDef    parent,  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff553-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ff553-107">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="ff553-108">진행 메타 데이터 형식 또는 메서드 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ff553-108">[in] The metadata type or method token.</span></span>  
  
 `name`  
 <span data-ttu-id="ff553-109">진행 필드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ff553-109">[in] The field name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="ff553-110">진행 필드 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ff553-110">[in] The field attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="ff553-111">진행 `ULONG32` 필드 시그니처를 포함 하는 데 필요한 버퍼의 크기 (문자 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="ff553-111">[in] A `ULONG32` that is the size, in characters, of the buffer required to contain the field signature.</span></span>  
  
 `signature`  
 <span data-ttu-id="ff553-112">진행 필드 시그니처의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ff553-112">[in] The array of field signatures.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="ff553-113">진행 주소 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="ff553-113">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="ff553-114">진행 필드 사양의 첫 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ff553-114">[in] The first address for the field specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="ff553-115">진행 필드 사양의 두 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ff553-115">[in] The second address for the field specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="ff553-116">진행 필드 사양의 세 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ff553-116">[in] The third address for the field specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff553-117">Return Value</span><span class="sxs-lookup"><span data-stu-id="ff553-117">Return Value</span></span>  

 <span data-ttu-id="ff553-118">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ff553-118">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff553-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff553-119">Requirements</span></span>  

 <span data-ttu-id="ff553-120">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="ff553-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff553-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff553-121">See also</span></span>

- [<span data-ttu-id="ff553-122">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff553-122">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)

---
title: ISymUnmanagedConstant::GetName 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetName
helpviewer_keywords:
- ISymUnmanagedConstant::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedConstant interface [.NET Framework debugging]
ms.assetid: cbaca4e1-4473-459b-ba34-f1f59ce7c0ba
topic_type:
- apiref
ms.openlocfilehash: fca7b11a83b5a695feae82fe5f25218f87afbce2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732894"
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="17d41-102">ISymUnmanagedConstant::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="17d41-102">ISymUnmanagedConstant::GetName Method</span></span>

<span data-ttu-id="17d41-103">상수의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="17d41-103">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17d41-104">구문</span><span class="sxs-lookup"><span data-stu-id="17d41-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17d41-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="17d41-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="17d41-106">진행 매개 변수가 가리키는 버퍼의 길이입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="17d41-106">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="17d41-107">제한이 `ULONG32` Null 종료를 포함 하 여 이름을 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="17d41-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="17d41-108">제한이 이름을 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="17d41-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17d41-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="17d41-109">Return Value</span></span>  

 <span data-ttu-id="17d41-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="17d41-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17d41-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="17d41-111">Requirements</span></span>  

 <span data-ttu-id="17d41-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="17d41-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17d41-113">참조</span><span class="sxs-lookup"><span data-stu-id="17d41-113">See also</span></span>

- [<span data-ttu-id="17d41-114">ISymUnmanagedConstant 인터페이스</span><span class="sxs-lookup"><span data-stu-id="17d41-114">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="17d41-115">GetSignature 메서드</span><span class="sxs-lookup"><span data-stu-id="17d41-115">GetSignature Method</span></span>](isymunmanagedconstant-getsignature-method.md)
- [<span data-ttu-id="17d41-116">GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="17d41-116">GetValue Method</span></span>](isymunmanagedconstant-getvalue-method.md)

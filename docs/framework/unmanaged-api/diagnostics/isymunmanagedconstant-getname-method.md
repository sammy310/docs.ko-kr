---
description: '자세히 알아보기: ISymUnmanagedConstant:: GetName 메서드'
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
ms.openlocfilehash: 57531711ed60c9e35e749a3cb1f1ba5d5c48ca66
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689822"
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="06085-103">ISymUnmanagedConstant::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="06085-103">ISymUnmanagedConstant::GetName Method</span></span>

<span data-ttu-id="06085-104">상수의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="06085-104">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06085-105">구문</span><span class="sxs-lookup"><span data-stu-id="06085-105">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06085-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="06085-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="06085-107">진행 매개 변수가 가리키는 버퍼의 길이입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="06085-107">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="06085-108">제한이 `ULONG32` Null 종료를 포함 하 여 이름을 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="06085-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="06085-109">제한이 이름을 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="06085-109">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06085-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="06085-110">Return Value</span></span>  

 <span data-ttu-id="06085-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="06085-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06085-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="06085-112">Requirements</span></span>  

 <span data-ttu-id="06085-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="06085-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06085-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06085-114">See also</span></span>

- [<span data-ttu-id="06085-115">ISymUnmanagedConstant 인터페이스</span><span class="sxs-lookup"><span data-stu-id="06085-115">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="06085-116">GetSignature 메서드</span><span class="sxs-lookup"><span data-stu-id="06085-116">GetSignature Method</span></span>](isymunmanagedconstant-getsignature-method.md)
- [<span data-ttu-id="06085-117">GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="06085-117">GetValue Method</span></span>](isymunmanagedconstant-getvalue-method.md)

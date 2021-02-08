---
description: '자세히 알아보기: ISymUnmanagedReader:: GetMethodByVersion 메서드'
title: ISymUnmanagedReader::GetMethodByVersion 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodByVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodByVersion
helpviewer_keywords:
- ISymUnmanagedReader::GetMethodByVersion method [.NET Framework debugging]
- GetMethodByVersion method [.NET Framework debugging]
ms.assetid: 6ddb0631-4569-41b3-93e4-50fdfaa486dc
topic_type:
- apiref
ms.openlocfilehash: 6b2fa3ff3af91d59bb79029d039e5656610bebff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772070"
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a><span data-ttu-id="8ba8c-103">ISymUnmanagedReader::GetMethodByVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="8ba8c-103">ISymUnmanagedReader::GetMethodByVersion Method</span></span>

<span data-ttu-id="8ba8c-104">메서드 토큰과 편집 및 복사 버전 번호가 지정 된 경우 기호 판독기 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8ba8c-104">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span> <span data-ttu-id="8ba8c-105">버전 번호는 1부터 시작 하 여 편집 및 복사 작업의 결과로 메서드가 변경 될 때마다 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba8c-105">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ba8c-106">구문</span><span class="sxs-lookup"><span data-stu-id="8ba8c-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ba8c-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8ba8c-107">Parameters</span></span>  

 `token`  
 <span data-ttu-id="8ba8c-108">진행 메서드 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8ba8c-108">[in] The method token.</span></span>  
  
 `version`  
 <span data-ttu-id="8ba8c-109">진행 메서드 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="8ba8c-109">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="8ba8c-110">제한이 반환 된 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8ba8c-110">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ba8c-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="8ba8c-111">Return Value</span></span>  

 <span data-ttu-id="8ba8c-112">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="8ba8c-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ba8c-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8ba8c-113">Requirements</span></span>  

 <span data-ttu-id="8ba8c-114">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="8ba8c-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ba8c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ba8c-115">See also</span></span>

- [<span data-ttu-id="8ba8c-116">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ba8c-116">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)

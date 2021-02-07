---
description: '자세히 알아보기: ISymUnmanagedDocument:: GetSourceLength 메서드'
title: ISymUnmanagedDocument::GetSourceLength 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceLength
helpviewer_keywords:
- GetSourceLength method [.NET Framework debugging]
- ISymUnmanagedDocument::GetSourceLength method [.NET Framework debugging]
ms.assetid: e087dbbb-f4fb-4fbe-8292-e4f1a14d0df2
topic_type:
- apiref
ms.openlocfilehash: 91ac1327afc84458c87122dddc31d0f5b2186f10
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721517"
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a><span data-ttu-id="5d79e-103">ISymUnmanagedDocument::GetSourceLength 메서드</span><span class="sxs-lookup"><span data-stu-id="5d79e-103">ISymUnmanagedDocument::GetSourceLength Method</span></span>

<span data-ttu-id="5d79e-104">포함 리소스의 길이(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5d79e-104">Gets the length, in bytes, of the embedded source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d79e-105">구문</span><span class="sxs-lookup"><span data-stu-id="5d79e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d79e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5d79e-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="5d79e-107">제한이 포함 된 소스의 길이 (바이트)를 나타내는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5d79e-107">[out] A pointer to a variable that indicates the length, in bytes, of the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d79e-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="5d79e-108">Return Value</span></span>  

 <span data-ttu-id="5d79e-109">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d79e-109">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d79e-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d79e-110">See also</span></span>

- [<span data-ttu-id="5d79e-111">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d79e-111">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)

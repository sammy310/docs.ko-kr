---
description: '자세한 정보: DLL을 로드 하는 동안 오류 발생 (Visual Basic)'
title: DLL을 로드하는 동안 오류가 발생했습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: 098d05e93d328f3667000bd81290f4b77cf7949e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796511"
---
# <a name="error-in-loading-dll-visual-basic"></a><span data-ttu-id="734e2-103">DLL을 로드하는 동안 오류가 발생했습니다(Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="734e2-103">Error in loading DLL (Visual Basic)</span></span>

<span data-ttu-id="734e2-104">DLL (동적 연결 라이브러리)은 문의 절에 지정 된 라이브러리입니다 `Lib` `Declare` .</span><span class="sxs-lookup"><span data-stu-id="734e2-104">A dynamic-link library (DLL) is a library specified in the `Lib` clause of a `Declare` statement.</span></span> <span data-ttu-id="734e2-105">이 오류의 가능한 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="734e2-105">Possible causes for this error include:</span></span>  
  
- <span data-ttu-id="734e2-106">파일이 DLL 실행 파일이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="734e2-106">The file is not DLL executable.</span></span>  
  
- <span data-ttu-id="734e2-107">파일이 Microsoft Windows DLL이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="734e2-107">The file is not a Microsoft Windows DLL.</span></span>  
  
- <span data-ttu-id="734e2-108">DLL이 존재 하지 않는 다른 DLL을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="734e2-108">The DLL references another DLL that is not present.</span></span>  
  
- <span data-ttu-id="734e2-109">DLL 또는 참조 된 DLL이 경로에 지정 된 디렉터리에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="734e2-109">The DLL or referenced DLL is not in a directory specified in the path.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="734e2-110">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="734e2-110">To correct this error</span></span>  
  
- <span data-ttu-id="734e2-111">파일이 원본 텍스트 파일 이며 DLL 실행 파일이 아닌 경우이 파일을 컴파일하여 DLL 실행 파일 폼에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="734e2-111">If the file is a source-text file and therefore not DLL executable, it must be compiled and linked to a DLL-executable form.</span></span>  
  
- <span data-ttu-id="734e2-112">파일이 Microsoft Windows DLL이 아닌 경우에는 Microsoft Windows를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="734e2-112">If the file is not a Microsoft Windows DLL, obtain the Microsoft Windows equivalent.</span></span>  
  
- <span data-ttu-id="734e2-113">DLL이 존재 하지 않는 다른 DLL을 참조 하는 경우 참조 된 DLL을 가져와 사용 가능 하 게 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="734e2-113">If the DLL references another DLL that is not present, obtain the referenced DLL and make it available.</span></span>  
  
- <span data-ttu-id="734e2-114">DLL 또는 참조 DLL이 경로에 지정 된 디렉터리에 없으면 DLL을 참조 된 디렉터리로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="734e2-114">If the DLL or referenced DLL is not in a directory specified by the path, move the DLL to a referenced directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="734e2-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="734e2-115">See also</span></span>

- [<span data-ttu-id="734e2-116">Declare 문</span><span class="sxs-lookup"><span data-stu-id="734e2-116">Declare Statement</span></span>](../statements/declare-statement.md)

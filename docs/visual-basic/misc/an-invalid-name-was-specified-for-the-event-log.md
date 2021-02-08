---
description: '자세히 알아보기: 이벤트 로그에 대해 잘못 된 이름이 지정 되었습니다.'
title: 이벤트 로그에 대해 잘못된 이름을 지정했습니다.
ms.date: 07/20/2015
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
ms.openlocfilehash: 4786483fe0b1ae32a16b67bfb4f406587719011b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787372"
---
# <a name="an-invalid-name-was-specified-for-the-event-log"></a><span data-ttu-id="d4427-103">이벤트 로그에 대해 잘못된 이름을 지정했습니다.</span><span class="sxs-lookup"><span data-stu-id="d4427-103">An invalid name was specified for the event log</span></span>

<span data-ttu-id="d4427-104">이벤트 로그에 대해 잘못된 이름을 지정했습니다.</span><span class="sxs-lookup"><span data-stu-id="d4427-104">An invalid name was specified for the event log.</span></span> <span data-ttu-id="d4427-105">일반적으로 이름, 빈 파일 이름 또는 너무 긴 파일 이름에 잘못된 문자가 포함되어 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d4427-105">Usually this is a result of invalid characters in the name, a blank file name, or a file name that is too long.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d4427-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="d4427-106">To correct this error</span></span>  
  
- <span data-ttu-id="d4427-107">지정된 이름이 8자보다 긴 경우 다른 이벤트 로그 이름과 충돌하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4427-107">If the specified name is more than eight characters, make sure there is no conflict with the names of other event logs.</span></span> <span data-ttu-id="d4427-108">이름이 고유한지 확인할 때 처음 8자만 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="d4427-108">Only the first eight characters are evaluated when determining if the name is unique.</span></span>  
  
- <span data-ttu-id="d4427-109">경로를 제공하는 경우 제대로 구문 분석되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4427-109">If supplying a path, make sure it is parsed correctly.</span></span>  
  
- <span data-ttu-id="d4427-110">이름에 잘못된 문자가 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d4427-110">Check that there are no invalid characters in the name.</span></span> <span data-ttu-id="d4427-111">`<`, `>`, `:`, `"`, `/`, `\`및 `|`는 파일 이름에 사용할 수 없는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="d4427-111">Characters that cannot be used in a file name include `<`, `>`, `:`, `"`, `/`, `\`, and `|`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4427-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4427-112">See also</span></span>

- [<span data-ttu-id="d4427-113">방법: 파일 경로 구문 분석</span><span class="sxs-lookup"><span data-stu-id="d4427-113">How to: Parse File Paths</span></span>](../developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
- [<span data-ttu-id="d4427-114">방법: 파일 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="d4427-114">How to: Rename a File</span></span>](../developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)

---
title: '방법: 응용 프로그램 세션 간 설정 값 변경'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: c1626cea581e5c180665d0ce805dea3e67f27a05
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714361"
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="97b1e-102">방법: 응용 프로그램 세션 간 설정 값 변경</span><span class="sxs-lookup"><span data-stu-id="97b1e-102">How To: Change the Value of a Setting Between Application Sessions</span></span>
<span data-ttu-id="97b1e-103">때때로 다음 응용 프로그램을 컴파일 및 배포 후 응용 프로그램 세션 간 설정 값을 변경 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="97b1e-103">At times, you might want to change the value of a setting between application sessions after the application has been compiled and deployed.</span></span> <span data-ttu-id="97b1e-104">예를 들어, 다음 올바른 데이터베이스 위치를 가리키도록 연결 문자열을 변경 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="97b1e-104">For example, you might want to change a connection string to point to the correct database location.</span></span> <span data-ttu-id="97b1e-105">디자인 타임 도구를 사용할 수 없는 응용 프로그램을 컴파일 및 배포 후 하므로 파일에서 수동으로 설정 값을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97b1e-105">Since design-time tools are not available after the application has been compiled and deployed, you must change the setting value manually in the file.</span></span>  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="97b1e-106">응용 프로그램 세션 간 설정 값을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="97b1e-106">To Change the Value of a Setting Between Application Sessions</span></span>  
  
1.  <span data-ttu-id="97b1e-107">Microsoft 메모장 또는 일부 다른 텍스트 또는 XML 편집기를 사용 하 여, 응용 프로그램과 연결 된.config 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="97b1e-107">Using Microsoft Notepad or some other text or XML editor, open the .config file associated with your application.</span></span>  
  
2.  <span data-ttu-id="97b1e-108">변경 하려면 설정에 대 한 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="97b1e-108">Locate the entry for the setting you want to change.</span></span> <span data-ttu-id="97b1e-109">아래 예제와 비슷하게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97b1e-109">It should look similar to the example presented below.</span></span>  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  <span data-ttu-id="97b1e-110">설정에 대 한 새 값을 입력 하 고 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="97b1e-110">Type a new value for your setting and save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97b1e-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="97b1e-111">See also</span></span>
- [<span data-ttu-id="97b1e-112">응용 프로그램 설정 및 사용자 설정 사용</span><span class="sxs-lookup"><span data-stu-id="97b1e-112">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="97b1e-113">응용 프로그램 설정 개요</span><span class="sxs-lookup"><span data-stu-id="97b1e-113">Application Settings Overview</span></span>](application-settings-overview.md)

---
title: '방법: .NET Framework 3.0 설치 여부 확인'
ms.date: 03/30/2017
helpviewer_keywords:
- WinFX Runtime user-agent string
- presence of WPT [WPF], detecting
- detecting WPF presence [WPF]
ms.assetid: 7f71d652-1749-4379-945a-aa2e3994cb43
ms.openlocfilehash: 27f856b895f48dc2365a1721dbc90294269899c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947825"
---
# <a name="how-to-detect-whether-the-net-framework-30-is-installed"></a><span data-ttu-id="bc2c1-102">방법: .NET Framework 3.0 설치 여부 확인</span><span class="sxs-lookup"><span data-stu-id="bc2c1-102">How to: Detect Whether the .NET Framework 3.0 Is Installed</span></span>
<span data-ttu-id="bc2c1-103">시스템에서 Microsoft.NET Framework 응용 프로그램을 배포 하려면 관리자,.NET Framework 런타임 있는지 먼저 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2c1-103">Before administrators can deploy Microsoft .NET Framework applications on a system, they must first confirm that the .NET Framework runtime is present.</span></span> <span data-ttu-id="bc2c1-104">이 항목에서는 HTML/JavaScript로 작성 된 스크립트를 관리자가.NET Framework 시스템에 있는지 여부를 결정 하는 데 사용할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2c1-104">This topic provides a script written in HTML/JavaScript that administrators can use to determine whether the .NET Framework is present on a system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc2c1-105">설치에 대 한 정보를 자세한 배포 및 Microsoft.NET Framework 검색 참조의 설명을 [배포 하는 Microsoft.NET Framework 버전 3.0](https://go.microsoft.com/fwlink/?LinkId=96739)합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2c1-105">For more detailed information on installing, deploying, and detecting the Microsoft .NET Framework, see the discussion in [Deploying Microsoft .NET Framework Version 3.0](https://go.microsoft.com/fwlink/?LinkId=96739).</span></span>  
  
<a name="content_expiration"></a>   
## <a name="detect-the-net-clr-user-agent-string"></a><span data-ttu-id="bc2c1-106">".NET CLR" 사용자 에이전트 문자열 검색</span><span class="sxs-lookup"><span data-stu-id="bc2c1-106">Detect the ".NET CLR" User-Agent String</span></span>  
 <span data-ttu-id="bc2c1-107">.NET Framework를 설치 하면 MSI UserAgent 문자열에 ".NET CLR" 및 버전 번호를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2c1-107">When .NET Framework is installed, the MSI adds ".NET CLR" and the version number to the UserAgent string.</span></span> <span data-ttu-id="bc2c1-108">다음 예제에서는 간단한 HTML 페이지에 포함 된 스크립트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc2c1-108">The following example shows a script embedded in a simple HTML page.</span></span> <span data-ttu-id="bc2c1-109">.NET Framework가 설치 되어 있는지 여부를 확인 하는 검색 결과에 상태 메시지를 표시 하려면 UserAgent 문자열을 검색 하는 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="bc2c1-109">The script searches the UserAgent string to determine whether .NET Framework is installed, and displays a status message on the results of the search.</span></span>  
  
```  
<HTML>  
  <HEAD>  
    <TITLE>Test for the .NET Framework 3.0</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT LANGUAGE="JavaScript">  
    <!--  
    var dotNETRuntimeVersion = "3.0.04425.00";  
  
    function window::onload()  
    {  
      if (HasRuntimeVersion(dotNETRuntimeVersion))  
      {  
        result.innerText =   
          "This machine has the correct version of the .NET Framework 3.0: "   
          + dotNETRuntimeVersion  
      }   
      else  
      {  
        result.innerText =   
          "This machine does not have the correct version of the .NET Framework 3.0."  
      }  
      result.innerText += "\n\nThis machine's userAgent string is: " +   
        navigator.userAgent + ".";  
    }  
  
    //  
    // Retrieve the version from the user agent string and   
    // compare with the specified version.  
    //  
    function HasRuntimeVersion(versionToCheck)  
    {  
      var userAgentString =   
        navigator.userAgent.match(/.NET CLR [0-9.]+/g);  
  
      if (userAgentString != null)  
      {  
        var i;  
  
        for (i = 0; i < userAgentString.length; ++i)  
        {  
          if (CompareVersions(GetVersion(versionToCheck),   
            GetVersion(userAgentString[i])) <= 0)  
            return true;  
        }  
      }  
  
      return false;  
    }  
  
    //  
    // Extract the numeric part of the version string.  
    //  
    function GetVersion(versionString)  
    {  
      var numericString =   
        versionString.match(/([0-9]+)\.([0-9]+)\.([0-9]+)/i);  
      return numericString.slice(1);  
    }  
  
    //  
    // Compare the 2 version strings by converting them to numeric format.  
    //  
    function CompareVersions(version1, version2)  
    {  
      for (i = 0; i < version1.length; ++i)  
      {  
        var number1 = new Number(version1[i]);  
        var number2 = new Number(version2[i]);  
  
        if (number1 < number2)  
          return -1;  
  
        if (number1 > number2)  
          return 1;  
      }  
  
      return 0;  
    }  
  
    -->  
    </SCRIPT>  
  </HEAD>  
  
  <BODY>  
    <div id="result" />  
  </BODY>  
</HTML>  
```  
  
 <span data-ttu-id="bc2c1-110">".NET CLR" 버전에 대 한 검색이 성공 하면 다음과 같은 유형의 상태 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc2c1-110">If the search for the ".NET CLR " version is successful, the following type of status message appears:</span></span>  
  
 `This machine has the correct version of the .NET Framework 3.0: 3.0.04425.00`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; .NET CLR 1.1.4322; InfoPath.1; .NET CLR 2.0.50727; .NET CLR 3.0.04425.00).`  
  
 <span data-ttu-id="bc2c1-111">그렇지 않은 경우 다음과 같은 유형의 상태 메시지 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc2c1-111">Otherwise, the following type of status message appears:</span></span>  
  
 `This machine does not have correct version of the .NET Framework 3.0.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; .NET CLR 1.1.4322; InfoPath.1; .NET CLR 2.0.50727).`

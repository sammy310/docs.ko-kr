---
title: '방법: 글로벌 어셈블리 캐시의 내용 보기'
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, viewing contents
- viewing assemblies in global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- GAC (global assembly cache), viewing contents
- list of assemblies in global assembly cache
- Global Assembly Cache tool
ms.assetid: c5f786a0-969b-4f14-9f02-e77c3384d9af
ms.openlocfilehash: b5d8b31e7eb23789878da620f3a4517056a1ee3e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119826"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a>방법: 글로벌 어셈블리 캐시의 내용 보기

[전역 어셈블리 캐시 도구(Gacutil.exe)](../tools/gacutil-exe-gac-tool.md)를 사용하면 GAC(전역 어셈블리 캐시)의 콘텐츠를 볼 수 있습니다.

## <a name="view-the-assemblies-in-the-gac"></a>GAC의 어셈블리 보기

전역 어셈블리 캐시의 어셈블리 목록을 보려면 [Visual Studio에 대한 개발자 명령 프롬프트](../tools/developer-command-prompt-for-vs.md)를 열고 다음 명령을 입력합니다.

```shell
gacutil -l
```

또는

```shell
gacutil /l
```

> [!NOTE]
> 이전 버전의 .NET Framework에서는 [Shfusion.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) Windows 셸 확장을 통해 파일 탐색기에서 전역 어셈블리 캐시를 볼 수 있었습니다. .NET Framework 4부터는 Shfusion.dll이 사용되지 않습니다.

## <a name="see-also"></a>참조

- [어셈블리 및 전역 어셈블리 캐시 사용](working-with-assemblies-and-the-gac.md)
- [Gacutil.exe(전역 어셈블리 캐시 도구)](../tools/gacutil-exe-gac-tool.md)

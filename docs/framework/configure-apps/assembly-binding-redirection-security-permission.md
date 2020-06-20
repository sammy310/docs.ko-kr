---
title: 어셈블리 바인딩 리디렉션 보안 권한
description: .NET의 응용 프로그램 구성 파일에서 명시적 어셈블리 바인딩 리디렉션에 필요한 보안 권한에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
ms.openlocfilehash: a8596bcac4efb0aea07efcfde6726d8bbf148c24
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105090"
---
# <a name="assembly-binding-redirection-security-permission"></a>어셈블리 바인딩 리디렉션 보안 권한
애플리케이션 구성 파일에서 어셈블리 바인딩을 명시적으로 리디렉션하려면 보안 권한이 필요합니다. 이는 .NET Framework 어셈블리와 타사 어셈블리의 리디렉션 모두에 적용됩니다. 에 플래그를 설정 하 여 사용 권한을 부여 합니다 <xref:System.Security.Permissions.SecurityPermissionFlag> <xref:System.Security.Permissions.SecurityPermission> . 관리 되는 어셈블리에는 기본적으로 권한이 없습니다.  
  
 보안 권한은 신뢰할 수 있는 영역 (로컬 컴퓨터) 및 인트라넷 영역에서 실행 되는 응용 프로그램에 부여 됩니다. 인터넷 영역에서 실행 되는 응용 프로그램은 어셈블리 바인딩 리디렉션을 수행할 수 없습니다.  
  
 구성 요소 게시자가 제어 하는 게시자 정책 파일 또는 관리자가 제어 하는 컴퓨터 구성 파일에서 어셈블리 리디렉션을 수행 하는 경우에는이 권한이 필요 하지 않습니다. 그러나 응용 프로그램 [\<publisherPolicy apply="no"/>](./file-schema/runtime/publisherpolicy-element.md) 에서 응용 프로그램 구성 파일의 요소를 사용 하 여 게시자 정책을 명시적으로 무시 하려면 권한이 필요 합니다.  
  
 다음 표에서는 **Bindingredirects** 플래그에 대 한 기본 보안 설정을 보여 줍니다.  
  
|영역|BindingRedirects 플래그 설정|  
|----------|-----------------------------------|  
|신뢰할 수 있는 영역 (로컬 컴퓨터)|**ON**|  
|인트라넷 영역|**ON**|  
|인터넷 영역|**OFF**|  
|신뢰할 수 없는 영역|**OFF**|  
  
 관리자는 이러한 보안 설정을 변경 하 여 지정 된 컴퓨터의 특정 시나리오를 지원 하거나 제한할 수 있습니다. **바인딩 리디렉션** 플래그 설정을 기본값에서 변경 하는 데 사용할 수 있는 도구가 없습니다. 관리자는 사용자 컴퓨터에서 Security.config 파일을 수동으로 편집 해야 합니다.  
  
## <a name="see-also"></a>참고 항목

- [게시자 정책 파일 및 Side-by-Side 실행](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))
- [방법: 자동 바인딩 리디렉션 사용 설정 및 해제](how-to-enable-and-disable-automatic-binding-redirection.md)
- [Side-by-side 실행](../deployment/side-by-side-execution.md)

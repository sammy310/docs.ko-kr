---
title: 클라이언트 쪽 공급자 어셈블리 등록
description: 클라이언트 쪽 UI 자동화 공급자가 포함 된 DLL을 등록 하는 방법을 보여 주는 예제를 검토 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- registering client-side provider assemblies
- client-side provider assemblies, registering
- UI Automation, registering provider assemblies
- provider assemblies, registering
ms.assetid: a03af4d9-2771-43cc-b07b-d468dca23190
ms.openlocfilehash: 034a109bb69c08883c0943b7b6ef69a397a8e7e1
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168137"
---
# <a name="register-a-client-side-provider-assembly"></a>클라이언트 쪽 공급자 어셈블리 등록
> [!NOTE]
> 이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.  
  
 이 항목에서는 클라이언트 쪽 UI 자동화 공급자가 포함된 DLL을 등록하는 방법을 보여줍니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 콘솔 창에 대한 공급자가 포함된 어셈블리를 등록하는 방법을 보여줍니다.  
  
 [!code-csharp[UIAClientSideProvider_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSClientProgram.cs#102)]
 [!code-vb[UIAClientSideProvider_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csclientprogram.vb#102)]  
  
## <a name="see-also"></a>참고 항목

- [클라이언트 쪽 UI 자동화 공급자 만들기](create-a-client-side-ui-automation-provider.md)

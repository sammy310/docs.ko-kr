---
title: '방법: 애플리케이션 세션 간의 애플리케이션 범위 속성 유지 및 복원'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application-scope properties [WPF], persisting
- persisting application-scope properties [WPF]
- properties [WPF], persisting
- restoring application-scope properties [WPF]
- properties [WPF], restoring
- application-scope properties [WPF], restoring
ms.assetid: 55d5904a-f444-4eb5-abd3-6bc74dd14226
ms.openlocfilehash: 99b04060d4e7c14313655010dc4fbd5ce1c90487
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788676"
---
# <a name="how-to-persist-and-restore-application-scope-properties-across-application-sessions"></a>방법: 애플리케이션 세션 간의 애플리케이션 범위 속성 유지 및 복원
이 예제에서는 응용 프로그램은 다음 경우에 응용 프로그램 범위 속성 복원 시작 하는 방법 및 응용 프로그램 종료 될 때 응용 프로그램 범위 속성을 유지 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 응용 프로그램, 응용 프로그램 범위 속성 유지 및 격리 된 저장소에서 복원 합니다. 격리 된 저장소에 파일 액세스 권한 없이 응용 프로그램에서 안전 하 게 사용할 수 있는 보호 된 저장소 영역입니다.  *App.xaml* 파일에 정의 `App_Startup` 에 대 한 처리기 메서드를 <xref:System.Windows.Application.Startup?displayProperty=nameWithType> 이벤트 및 `App_Exit` 에 대 한 처리기 메서드는 <xref:System.Windows.Application.Exit?displayProperty=nameWithType> 이벤트를 강조 표시 된 줄의 첫 번째 예제에 나와 있는 것 처럼. 두 번째 예의 일부를 보여 줍니다.는 *App.xaml.cs* 하 고 *App.xaml.vb* 파일에 대 한 코드를 강조 표시 하는 `App_Startup` 응용 프로그램 범위 속성 및 합니다 복원하는메서드를`App_Exit` 메서드를 응용 프로그램 범위 속성을 저장 합니다.

 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=17-55)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistrestoreappscopepropertiescodebehind1)]

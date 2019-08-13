---
title: 在传统 Web 应用和单页应用之间选择
description: 了解在生成 Web 应用时，如何在传统 Web 应用和单页应用程序 (SPA) 之间进行选择。
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
ms.openlocfilehash: d68c167dce791a31eeb5ca5729b50ec22c64f9b0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68675474"
---
# <a name="choose-between-traditional-web-apps-and-single-page-apps-spas"></a><span data-ttu-id="7d4c9-103">在传统 Web 应用和单页应用 (SPA) 之间选择</span><span class="sxs-lookup"><span data-stu-id="7d4c9-103">Choose Between Traditional Web Apps and Single Page Apps (SPAs)</span></span>

> <span data-ttu-id="7d4c9-104">“Atwood 定律：任何能够用 JavaScript 编写的应用程序，最终必将用 JavaScript 编写。”</span><span class="sxs-lookup"><span data-stu-id="7d4c9-104">"Atwood's Law: Any application that can be written in JavaScript, will eventually be written in JavaScript."</span></span>  
> <span data-ttu-id="7d4c9-105">\- Jeff Atwood </span><span class="sxs-lookup"><span data-stu-id="7d4c9-105">_\- Jeff Atwood_</span></span>

<span data-ttu-id="7d4c9-106">目前可通过两种通用方法来构建 Web 应用程序：在服务器上执行大部分应用程序逻辑的传统 Web 应用程序，以及在 Web 浏览器中执行大部分用户界面逻辑的单页应用程序 (SPA)，后者主要使用 Web API 与 Web 服务器通信。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-106">There are two general approaches to building web applications today: traditional web applications that perform most of the application logic on the server, and single page applications (SPAs) that perform most of the user interface logic in a web browser, communicating with the web server primarily using web APIs.</span></span> <span data-ttu-id="7d4c9-107">也可以将两种方法混合使用，最简单的方法是在更大型的传统 Web 应用程序中承载一个或多个丰富 SPA 类子应用程序。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-107">A hybrid approach is also possible, the simplest being host one or more rich SPA-like sub-applications within a larger traditional web application.</span></span>

<span data-ttu-id="7d4c9-108">何时应使用传统 Web 应用程序：</span><span class="sxs-lookup"><span data-stu-id="7d4c9-108">You should use traditional web applications when:</span></span>

- <span data-ttu-id="7d4c9-109">应用程序的客户端要求简单，甚至要求只读。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-109">Your application's client-side requirements are simple or even read-only.</span></span>

- <span data-ttu-id="7d4c9-110">应用程序需在不支持 JavaScript 的浏览器中工作。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-110">Your application needs to function in browsers without JavaScript support.</span></span>

- <span data-ttu-id="7d4c9-111">团队不熟悉 JavaScript 或 TypeScript 开发技术。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-111">Your team is unfamiliar with JavaScript or TypeScript development techniques.</span></span>

<span data-ttu-id="7d4c9-112">何时应使用 SPA：</span><span class="sxs-lookup"><span data-stu-id="7d4c9-112">You should use a SPA when:</span></span>

- <span data-ttu-id="7d4c9-113">应用程序必须公开具有许多功能的丰富用户界面。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-113">Your application must expose a rich user interface with many features.</span></span>

- <span data-ttu-id="7d4c9-114">团队熟悉 JavaScript 和/或 TypeScript 开发。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-114">Your team is familiar with JavaScript and/or TypeScript development.</span></span>

- <span data-ttu-id="7d4c9-115">应用程序已为其他（内部或公共）客户端公开 API。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-115">Your application must already expose an API for other (internal or public) clients.</span></span>

<span data-ttu-id="7d4c9-116">此外，SPA 框架还需要更强的体系结构和安全专业知识。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-116">Additionally, SPA frameworks require greater architectural and security expertise.</span></span> <span data-ttu-id="7d4c9-117">相较于传统 Web 应用程序，SPA 框架需要进行频繁的更新和使用新框架，因此改动更大。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-117">They experience greater churn due to frequent updates and new frameworks than traditional web applications.</span></span> <span data-ttu-id="7d4c9-118">相较于传统 Web 应用，SPA 应用程序在配置自动化生成和部署过程以及利用部署选项（如容器）方面的难度更大。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-118">Configuring automated build and deployment processes and utilizing deployment options like containers are more difficult with SPA applications than traditional web apps.</span></span>

<span data-ttu-id="7d4c9-119">使用 SPA 模型改进用户体验时必须权衡这些注意事项。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-119">Improvements in user experience made possible by SPA model must be weighed against these considerations.</span></span>

## <a name="blazor"></a><span data-ttu-id="7d4c9-120">Blazor</span><span class="sxs-lookup"><span data-stu-id="7d4c9-120">Blazor</span></span>

<span data-ttu-id="7d4c9-121">ASP.NET Core 3.0 引入了一种新模型，用于构建称为 Blazor 的丰富的、交互式和可组合的 UI。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-121">ASP.NET Core 3.0 introduces a new model for building rich, interactive, and composable UI called Blazor.</span></span> <span data-ttu-id="7d4c9-122">Blazor 服务器端允许开发人员在服务器上使用 Razor 构建 UI，并使用名为 WebAssembly 的 JavaScript 库将此代码传递到浏览器和执行客户端。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-122">Blazor server-side allows developers to build UI with Razor on the server and for this code to be delivered to the browser and executed client-side using a JavaScript library called WebAssembly.</span></span> <span data-ttu-id="7d4c9-123">ASP.NET Core 3.0 仍在开发中，但你应该会期望在本电子书的 3.0 更新中看到有关此技术的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-123">ASP.NET Core 3.0 is still under development, but you should expect to see more on this technology in the 3.0 update to this e-book.</span></span> <span data-ttu-id="7d4c9-124">有关 Blazor 的详细信息，请参阅 [Blazor 入门](https://blazor.net/docs/get-started.html)。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-124">For more information about Blazor, see [Get started with Blazor](https://blazor.net/docs/get-started.html).</span></span>

## <a name="when-to-choose-traditional-web-apps"></a><span data-ttu-id="7d4c9-125">何时选择传统 Web 应用</span><span class="sxs-lookup"><span data-stu-id="7d4c9-125">When to choose traditional web apps</span></span>

<span data-ttu-id="7d4c9-126">以下内容详细介绍前面提到的选择传统 Web 应用程序的原因。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-126">The following is a more detailed explanation of the previously stated reasons for picking traditional web applications.</span></span>

<span data-ttu-id="7d4c9-127">**应用程序的客户端要求简单，可能要求只读**</span><span class="sxs-lookup"><span data-stu-id="7d4c9-127">**Your application has simple, possibly read-only, client-side requirements**</span></span>

<span data-ttu-id="7d4c9-128">对许多 Web 应用程序而言，其大部分用户的主要使用方式是只读。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-128">Many web applications are primarily consumed in a read-only fashion by the vast majority of their users.</span></span> <span data-ttu-id="7d4c9-129">只读（或以读取为主）应用程序往往比那些维护和操作大量状态的应用程序简单得多。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-129">Read-only (or read-mostly) applications tend to be much simpler than those that maintain and manipulate a great deal of state.</span></span> <span data-ttu-id="7d4c9-130">例如，搜索引擎可能由一个带有文本框的入口点和用于显示搜索结果的第二页组成。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-130">For example, a search engine might consist of a single entry point with a textbox and a second page for displaying search results.</span></span> <span data-ttu-id="7d4c9-131">匿名用户可以轻松提出请求，并且很少需要使用客户端逻辑。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-131">Anonymous users can easily make requests, and there is little need for client-side logic.</span></span> <span data-ttu-id="7d4c9-132">同样，一般而言，博客或内容管理系统中面向公众的应用程序主要包含的内容与客户端行为关系不大。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-132">Likewise, a blog or content management system's public-facing application usually consists mainly of content with little client-side behavior.</span></span> <span data-ttu-id="7d4c9-133">此类应用程序容易构建为基于服务器的传统 Web 应用程序，在 Web 服务器上执行逻辑，并呈现要在浏览器中显示的 HTML。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-133">Such applications are easily built as traditional server-based web applications which perform logic on the web server and render HTML to be displayed in the browser.</span></span> <span data-ttu-id="7d4c9-134">事实上，网站的每个独特页面都有自己的 URL，搜索引擎可以将其存为书签和编入索引（默认设置，无需将其添加为应用程序的单独功能），这也是此类情况的一个明显优势。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-134">The fact that each unique page of the site has its own URL that can be bookmarked and indexed by search engines (by default, without having to add this as a separate feature of the application) is also a clear benefit in such scenarios.</span></span>

<span data-ttu-id="7d4c9-135">**应用程序需在不支持 JavaScript 的浏览器中工作**</span><span class="sxs-lookup"><span data-stu-id="7d4c9-135">**Your application needs to function in browsers without JavaScript support**</span></span>

<span data-ttu-id="7d4c9-136">如需在有限或不支持 JavaScript 的浏览器中工作的 Web 应用程序，则应使用传统的 Web 应用工作流编写（或至少可以回退到此类行为）。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-136">Web applications that need to function in browsers with limited or no JavaScript support should be written using traditional web app workflows (or at least be able to fall back to such behavior).</span></span> <span data-ttu-id="7d4c9-137">SPA 需要客户端 JavaScript 才能正常工作；如果没有客户端 JavaScript，SPA 不是好的选择。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-137">SPAs require client-side JavaScript in order to function; if it's not available, SPAs are not a good choice.</span></span>

<span data-ttu-id="7d4c9-138">**团队不熟悉 JavaScript 或 TypeScript 开发技术**</span><span class="sxs-lookup"><span data-stu-id="7d4c9-138">**Your team is unfamiliar with JavaScript or TypeScript development techniques**</span></span>

<span data-ttu-id="7d4c9-139">如果团队不熟悉 JavaScript 或 TypeScript，但熟悉服务器端 Web 应用程序开发，那相较于 SPA，他们交付传统 Web 应用的速度可能更快。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-139">If your team is unfamiliar with JavaScript or TypeScript, but is familiar with server-side web application development, then they will probably be able to deliver a traditional web app more quickly than a SPA.</span></span> <span data-ttu-id="7d4c9-140">除非以学习 SPA 编程为目的，或需要 SPA 提供用户体验，否则对已经熟悉构建传统 Web 应用的团队而言，选择传统 Web 应用的工作效率更高。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-140">Unless learning to program SPAs is a goal, or the user experience afforded by a SPA is required, traditional web apps are a more productive choice for teams who are already familiar with building them.</span></span>

## <a name="when-to-choose-spas"></a><span data-ttu-id="7d4c9-141">何时选择 SPA</span><span class="sxs-lookup"><span data-stu-id="7d4c9-141">When to choose SPAs</span></span>

<span data-ttu-id="7d4c9-142">以下内容详细介绍何时为 Web 应用选择单页应用程序开发样式。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-142">The following is a more detailed explanation of when to choose a Single Page Applications style of development for your web app.</span></span>

<span data-ttu-id="7d4c9-143">**应用程序必须公开具有许多功能的丰富用户界面**</span><span class="sxs-lookup"><span data-stu-id="7d4c9-143">**Your application must expose a rich user interface with many features**</span></span>

<span data-ttu-id="7d4c9-144">SPA 可支持丰富客户端功能，当用户执行操作或在应用的各区域间导航时无需重新加载页面。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-144">SPAs can support rich client-side functionality that doesn't require reloading the page as users take actions or navigate between areas of the app.</span></span> <span data-ttu-id="7d4c9-145">SPA 很少需要重新加载整个页面，因此加载速度更快，可在后台提取数据，并且对单个用户操作的响应更快。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-145">SPAs can load more quickly, fetching data in the background, and individual user actions are more responsive since full page reloads are rare.</span></span> <span data-ttu-id="7d4c9-146">SPA 支持增量更新，可保存尚未完成的窗体或文档，而无需用户单击按钮提交窗体。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-146">SPAs can support incremental updates, saving partially completed forms or documents without the user having to click a button to submit a form.</span></span> <span data-ttu-id="7d4c9-147">SPA 支持丰富的客户端行为，例如拖放，比传统应用程序更容易操作。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-147">SPAs can support rich client-side behaviors, such as drag-and-drop, much more readily than traditional applications.</span></span> <span data-ttu-id="7d4c9-148">可以将 SPA 设计为在断开连接的模式下运行，对客户端模型进行更新，并在重新建立连接后将更新最终同步回服务器。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-148">SPAs can be designed to run in a disconnected mode, making updates to a client-side model that are eventually synchronized back to the server once a connection is re-established.</span></span> <span data-ttu-id="7d4c9-149">如果应用要求包括丰富的功能，且超出了典型 HTML 窗体提供的功能，则应选择 SPA 样式应用程序。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-149">You should choose a SPA style application if your app's requirements include rich functionality that goes beyond what typical HTML forms offer.</span></span>

<span data-ttu-id="7d4c9-150">请注意，SPA 通常需要实现内置于传统 Web 应用中的功能，例如在反映当前操作的地址栏中显示有意义的 URL（并允许用户将此 URL 存为书签或对其进行深层链接以便返回此 URL）。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-150">Note that frequently SPAs need to implement features that are built-in to traditional web apps, such as displaying a meaningful URL in the address bar reflecting the current operation (and allowing users to bookmark or deep link to this URL to return to it).</span></span> <span data-ttu-id="7d4c9-151">SPA 还应允许用户使用浏览器的后退和前进按钮寻找用户意料之中的结果。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-151">SPAs also should allow users to use the browser's back and forward buttons with results that won't surprise them.</span></span>

<span data-ttu-id="7d4c9-152">**团队熟悉 JavaScript 和/或 TypeScript 开发**</span><span class="sxs-lookup"><span data-stu-id="7d4c9-152">**Your team is familiar with JavaScript and/or TypeScript development**</span></span>

<span data-ttu-id="7d4c9-153">编写 SPA 需要熟悉 JavaScript 和/或 TypeScript 以及客户端编程技术和库。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-153">Writing SPAs requires familiarity with JavaScript and/or TypeScript and client-side programming techniques and libraries.</span></span> <span data-ttu-id="7d4c9-154">团队应有能力像使用 Angular 一样使用 SPA 框架编写新式 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-154">Your team should be competent in writing modern JavaScript using a SPA framework like Angular.</span></span>

> ### <a name="references--spa-frameworks"></a><span data-ttu-id="7d4c9-155">参考 - SPA 框架</span><span class="sxs-lookup"><span data-stu-id="7d4c9-155">References – SPA Frameworks</span></span>
>
> - <span data-ttu-id="7d4c9-156">**Angular**</span><span class="sxs-lookup"><span data-stu-id="7d4c9-156">**Angular**</span></span>  
>   <https://angular.io>
> - <span data-ttu-id="7d4c9-157">**JavaScript 框架的比较**</span><span class="sxs-lookup"><span data-stu-id="7d4c9-157">**Comparison of JavaScript Frameworks**</span></span>  
>   <https://jsreport.io/the-ultimate-guide-to-javascript-frameworks/>

<span data-ttu-id="7d4c9-158">**应用程序已为其他（内部或公共）客户端公开 API**</span><span class="sxs-lookup"><span data-stu-id="7d4c9-158">**Your application must already expose an API for other (internal or public) clients**</span></span>

<span data-ttu-id="7d4c9-159">如果已提供一个 Web API 供其他客户端使用，则相较于在服务器端窗体中复制逻辑，创建一个利用这些 API 的 SPA 实现更加容易。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-159">If you're already supporting a web API for use by other clients, it may require less effort to create a SPA implementation that leverages these APIs rather than reproducing the logic in server-side form.</span></span> <span data-ttu-id="7d4c9-160">用户与应用程序交互时，SPA 广泛使用 Web API 来查询和更新数据。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-160">SPAs make extensive use of web APIs to query and update data as users interact with the application.</span></span>

## <a name="decision-table--traditional-web-or-spa"></a><span data-ttu-id="7d4c9-161">决策表 - 传统 Web 或 SPA</span><span class="sxs-lookup"><span data-stu-id="7d4c9-161">Decision table – Traditional Web or SPA</span></span>

<span data-ttu-id="7d4c9-162">下面的决策表总结了在传统 Web 应用程序和 SPA 之间进行选择时要考虑的一些基本因素。</span><span class="sxs-lookup"><span data-stu-id="7d4c9-162">The following decision table summarizes some of the basic factors to consider when choosing between a traditional web application and a SPA.</span></span>

| <span data-ttu-id="7d4c9-163">**因素**</span><span class="sxs-lookup"><span data-stu-id="7d4c9-163">**Factor**</span></span>                                           | <span data-ttu-id="7d4c9-164">**传统 Web 应用**</span><span class="sxs-lookup"><span data-stu-id="7d4c9-164">**Traditional Web App**</span></span> | <span data-ttu-id="7d4c9-165">**单页应用程序**</span><span class="sxs-lookup"><span data-stu-id="7d4c9-165">**Single Page Application**</span></span> |
| ---------------------------------------------------- | ----------------------- | --------------------------- |
| <span data-ttu-id="7d4c9-166">需要团队熟悉 JavaScript/TypeScript</span><span class="sxs-lookup"><span data-stu-id="7d4c9-166">Required Team Familiarity with JavaScript/TypeScript</span></span> | <span data-ttu-id="7d4c9-167">**最少**</span><span class="sxs-lookup"><span data-stu-id="7d4c9-167">**Minimal**</span></span>             | <span data-ttu-id="7d4c9-168">**必需**</span><span class="sxs-lookup"><span data-stu-id="7d4c9-168">**Required**</span></span>                |
| <span data-ttu-id="7d4c9-169">支持不带脚本的浏览器</span><span class="sxs-lookup"><span data-stu-id="7d4c9-169">Support Browsers without Scripting</span></span>                   | <span data-ttu-id="7d4c9-170">**支持**</span><span class="sxs-lookup"><span data-stu-id="7d4c9-170">**Supported**</span></span>           | <span data-ttu-id="7d4c9-171">**不支持**</span><span class="sxs-lookup"><span data-stu-id="7d4c9-171">**Not Supported**</span></span>           |
| <span data-ttu-id="7d4c9-172">客户端应用程序行为极少</span><span class="sxs-lookup"><span data-stu-id="7d4c9-172">Minimal Client-Side Application Behavior</span></span>             | <span data-ttu-id="7d4c9-173">**适合**</span><span class="sxs-lookup"><span data-stu-id="7d4c9-173">**Well-Suited**</span></span>         | <span data-ttu-id="7d4c9-174">**不必要**</span><span class="sxs-lookup"><span data-stu-id="7d4c9-174">**Overkill**</span></span>                |
| <span data-ttu-id="7d4c9-175">丰富而复杂的用户界面要求</span><span class="sxs-lookup"><span data-stu-id="7d4c9-175">Rich, Complex User Interface Requirements</span></span>            | <span data-ttu-id="7d4c9-176">**受限**</span><span class="sxs-lookup"><span data-stu-id="7d4c9-176">**Limited**</span></span>             | <span data-ttu-id="7d4c9-177">**适合**</span><span class="sxs-lookup"><span data-stu-id="7d4c9-177">**Well-Suited**</span></span>             |

>[!div class="step-by-step"]
><span data-ttu-id="7d4c9-178">[上一页](modern-web-applications-characteristics.md)
>[下一页](architectural-principles.md)</span><span class="sxs-lookup"><span data-stu-id="7d4c9-178">[Previous](modern-web-applications-characteristics.md)
[Next](architectural-principles.md)</span></span>
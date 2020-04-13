# Non-Persistent Objects Reloading Demo

This example demonstrates how non-persistnet objects with nested persistent objects can be refreshed. 

Non-persistent objects are kept in an object map. In the [NonPersistentObjectSpace\.ObjectsGetting](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.NonPersistentObjectSpace.ObjectsGetting?v=20.1), [NonPersistentObjectSpace\.ObjectGetting](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.NonPersistentObjectSpace.ObjectGetting), and [NonPersistentObjectSpace\.ObjectByKeyGetting](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.NonPersistentObjectSpace.ObjectByKeyGetting) event handlers, non-persistent objects are looked up and added to the object map. In the [Reloaded](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.BaseObjectSpace.Reloaded) event handler, the object map is cleared. So, subsequent object queries trigger the creation of new non-persistent object instances.

The [NonPersistentObjectSpace\.NeedReloadAdditionalObjectSpaces](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.NonPersistentObjectSpace.NeedReloadAdditionalObjectSpaces?v=20.1) property is set to *true* to automatically refresh persistent object spaces added to the [NonPersistentObjectSpace\.AdditionalObjectSpaces](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.NonPersistentObjectSpace.AdditionalObjectSpaces) collection. So, when non-persistent objects are re-created on refresh, they get fresh copies of nested persistent objects. 

The [NonPersistentObjectSpace\.NeedDisposeAdditionalObjectSpaces](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.NonPersistentObjectSpace.NeedDisposeAdditionalObjectSpaces?v=20.1) property is set to *true* to automatically dispose of additional object spaces when the non-persistent object space is disposed of. Disposing of unused object spaces is required to avoid memory leaks.

The non-persistent *LiveSummary* object in this example contains a collection of persistent objects, and some derived properties calculated from persistent objects that match parameters. After modifying persistent objects, use the built-in [Refresh](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.SystemModule.RefreshController.RefreshAction) action to completely reload non-persistent object views.

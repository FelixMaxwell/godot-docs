.. Generated automatically by doc/tools/makerst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the Curve.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_Curve:

Curve
=====

**Inherits:** :ref:`Resource<class_resource>` **<** :ref:`Reference<class_reference>` **<** :ref:`Object<class_object>`

**Category:** Core

Brief Description
-----------------

A mathematic curve.

Member Functions
----------------

+--------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`          | :ref:`add_point<class_Curve_add_point>` **(** :ref:`Vector2<class_vector2>` position, :ref:`float<class_float>` left_tangent=0, :ref:`float<class_float>` right_tangent=0, :ref:`int<class_int>` left_mode=0, :ref:`int<class_int>` right_mode=0 **)** |
+--------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                           | :ref:`bake<class_Curve_bake>` **(** **)**                                                                                                                                                                                                              |
+--------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                           | :ref:`clean_dupes<class_Curve_clean_dupes>` **(** **)**                                                                                                                                                                                                |
+--------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                           | :ref:`clear_points<class_Curve_clear_points>` **(** **)**                                                                                                                                                                                              |
+--------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`          | :ref:`get_point_left_mode<class_Curve_get_point_left_mode>` **(** :ref:`int<class_int>` index **)** const                                                                                                                                              |
+--------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`float<class_float>`      | :ref:`get_point_left_tangent<class_Curve_get_point_left_tangent>` **(** :ref:`int<class_int>` index **)** const                                                                                                                                        |
+--------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Vector2<class_vector2>`  | :ref:`get_point_position<class_Curve_get_point_position>` **(** :ref:`int<class_int>` index **)** const                                                                                                                                                |
+--------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`          | :ref:`get_point_right_mode<class_Curve_get_point_right_mode>` **(** :ref:`int<class_int>` index **)** const                                                                                                                                            |
+--------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`float<class_float>`      | :ref:`get_point_right_tangent<class_Curve_get_point_right_tangent>` **(** :ref:`int<class_int>` index **)** const                                                                                                                                      |
+--------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`float<class_float>`      | :ref:`interpolate<class_Curve_interpolate>` **(** :ref:`float<class_float>` offset **)** const                                                                                                                                                         |
+--------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`float<class_float>`      | :ref:`interpolate_baked<class_Curve_interpolate_baked>` **(** :ref:`float<class_float>` offset **)**                                                                                                                                                   |
+--------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                           | :ref:`remove_point<class_Curve_remove_point>` **(** :ref:`int<class_int>` index **)**                                                                                                                                                                  |
+--------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                           | :ref:`set_point_left_mode<class_Curve_set_point_left_mode>` **(** :ref:`int<class_int>` index, :ref:`int<class_int>` mode **)**                                                                                                                        |
+--------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                           | :ref:`set_point_left_tangent<class_Curve_set_point_left_tangent>` **(** :ref:`int<class_int>` index, :ref:`float<class_float>` tangent **)**                                                                                                           |
+--------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`          | :ref:`set_point_offset<class_Curve_set_point_offset>` **(** :ref:`int<class_int>` index, :ref:`float<class_float>` offset **)**                                                                                                                        |
+--------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                           | :ref:`set_point_right_mode<class_Curve_set_point_right_mode>` **(** :ref:`int<class_int>` index, :ref:`int<class_int>` mode **)**                                                                                                                      |
+--------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                           | :ref:`set_point_right_tangent<class_Curve_set_point_right_tangent>` **(** :ref:`int<class_int>` index, :ref:`float<class_float>` tangent **)**                                                                                                         |
+--------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                           | :ref:`set_point_value<class_Curve_set_point_value>` **(** :ref:`int<class_int>` index, :ref:`float<class_float>` y **)**                                                                                                                               |
+--------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Signals
-------

.. _class_Curve_range_changed:

- **range_changed** **(** **)**

Emitted when :ref:`max_value<class_Curve_max_value>` or :ref:`min_value<class_Curve_min_value>` is changed.


Member Variables
----------------

  .. _class_Curve_bake_resolution:

- :ref:`int<class_int>` **bake_resolution** - The number of points to include in the baked (i.e. cached) curve data.

  .. _class_Curve_max_value:

- :ref:`float<class_float>` **max_value** - The maximum value the curve can reach. Default value: ``1``.

  .. _class_Curve_min_value:

- :ref:`float<class_float>` **min_value** - The minimum value the curve can reach. Default value: ``0``.


Numeric Constants
-----------------

- **TANGENT_FREE** = **0** --- The tangent on this side of the point is user-defined.
- **TANGENT_LINEAR** = **1** --- The curve calculates the tangent on this side of the point as the slope halfway towards the adjacent point.
- **TANGENT_MODE_COUNT** = **2** --- The total number of available tangent modes.

Description
-----------

A curve that can be saved and re-used for other objects. By default it ranges between ``0`` and ``1`` on the y-axis and positions points relative to the ``0.5`` y-position.

Member Function Description
---------------------------

.. _class_Curve_add_point:

- :ref:`int<class_int>` **add_point** **(** :ref:`Vector2<class_vector2>` position, :ref:`float<class_float>` left_tangent=0, :ref:`float<class_float>` right_tangent=0, :ref:`int<class_int>` left_mode=0, :ref:`int<class_int>` right_mode=0 **)**

Adds a point to the curve. For each side, if the ``\*_mode`` is ``TANGENT_LINEAR``, the ``\*_tangent`` angle (in degrees) uses the slope of the curve halfway to the adjacent point. Allows custom assignments to the ``\*_tangent`` angle if ``\*_mode`` is set to ``TANGENT_FREE``.

.. _class_Curve_bake:

- void **bake** **(** **)**

Recomputes the baked cache of points for the curve.

.. _class_Curve_clean_dupes:

- void **clean_dupes** **(** **)**

Removes points that are closer than ``CMP_EPSILON`` (0.00001) units to their neighbor on the curve.

.. _class_Curve_clear_points:

- void **clear_points** **(** **)**

Removes all points from the curve.

.. _class_Curve_get_point_left_mode:

- :ref:`int<class_int>` **get_point_left_mode** **(** :ref:`int<class_int>` index **)** const

Returns the left ``TangentMode`` for the point at ``index``.

.. _class_Curve_get_point_left_tangent:

- :ref:`float<class_float>` **get_point_left_tangent** **(** :ref:`int<class_int>` index **)** const

Returns the left tangent angle (in degrees) for the point at ``index``.

.. _class_Curve_get_point_position:

- :ref:`Vector2<class_vector2>` **get_point_position** **(** :ref:`int<class_int>` index **)** const

Returns the curve coordinates for the point at ``index``.

.. _class_Curve_get_point_right_mode:

- :ref:`int<class_int>` **get_point_right_mode** **(** :ref:`int<class_int>` index **)** const

Returns the right ``TangentMode`` for the point at ``index``.

.. _class_Curve_get_point_right_tangent:

- :ref:`float<class_float>` **get_point_right_tangent** **(** :ref:`int<class_int>` index **)** const

Returns the right tangent angle (in degrees) for the point at ``index``.

.. _class_Curve_interpolate:

- :ref:`float<class_float>` **interpolate** **(** :ref:`float<class_float>` offset **)** const

Returns the y value for the point that would exist at x-position ``offset`` along the curve.

.. _class_Curve_interpolate_baked:

- :ref:`float<class_float>` **interpolate_baked** **(** :ref:`float<class_float>` offset **)**

Returns the y value for the point that would exist at x-position ``offset`` along the curve using the baked cache. Bakes the curve's points if not already baked.

.. _class_Curve_remove_point:

- void **remove_point** **(** :ref:`int<class_int>` index **)**

Removes the point at ``index`` from the curve.

.. _class_Curve_set_point_left_mode:

- void **set_point_left_mode** **(** :ref:`int<class_int>` index, :ref:`int<class_int>` mode **)**

Sets the left ``TangentMode`` for the point at ``index`` to ``mode``.

.. _class_Curve_set_point_left_tangent:

- void **set_point_left_tangent** **(** :ref:`int<class_int>` index, :ref:`float<class_float>` tangent **)**

Sets the left tangent angle for the point at ``index`` to ``tangent``.

.. _class_Curve_set_point_offset:

- :ref:`int<class_int>` **set_point_offset** **(** :ref:`int<class_int>` index, :ref:`float<class_float>` offset **)**

Sets the offset from ``0.5``

.. _class_Curve_set_point_right_mode:

- void **set_point_right_mode** **(** :ref:`int<class_int>` index, :ref:`int<class_int>` mode **)**

Sets the right ``TangentMode`` for the point at ``index`` to ``mode``.

.. _class_Curve_set_point_right_tangent:

- void **set_point_right_tangent** **(** :ref:`int<class_int>` index, :ref:`float<class_float>` tangent **)**

Sets the right tangent angle for the point at ``index`` to ``tangent``.

.. _class_Curve_set_point_value:

- void **set_point_value** **(** :ref:`int<class_int>` index, :ref:`float<class_float>` y **)**

Assigns the vertical position ``y`` to the point at ``index``.



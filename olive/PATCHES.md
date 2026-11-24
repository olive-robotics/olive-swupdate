# Local changes

Recorded on 2026-11-24; original implementation date is not established.

The payload's `core/util.c` differs from the identified upstream snapshot in
`check_free_space()`: both filesystem values are cast to `unsigned long long`
before multiplication, and the requested size is compared and logged using
the same width. This avoids overflow in the intermediate free-space
calculation. The exact payload implementation is retained unchanged.

The patch in `patches/0001-avoid-overflow-in-free-space-calculation.patch`
records the difference. Apply it only to an unmodified copy of upstream
`d3bab1ebd3c1ab51e740a963489bbe9af26c4474`; it is already applied in this
repository.

Publication additions are this documentation, `OLIVE-SOURCE.md`, the README
introduction, build configuration, manifest, integrity list and ignore rules.
Original upstream copyright and license notices are preserved.

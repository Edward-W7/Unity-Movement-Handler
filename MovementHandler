using UnityEngine;

public class MovementHandler : MonoBehaviour
{

    public float moveSpeed = 1f;
    public float maxSpeed = 1f;
    public float stopThreshold = 0f;

    public Rigidbody2D rb;
    public SpriteRenderer sprite;
    public Sprite f0;
    public Sprite f1;

    Vector2 movement;
    bool aniFrame1 = false;

    void ChangeSprite0()
    {
        sprite.sprite = f0;
        aniFrame1 = true;
    }

    void ChangeSprite1()
    {
        sprite.sprite = f1;
        aniFrame1 = false;
    }

    void Update()
    {

        movement.x = Input.GetAxisRaw("Horizontal");
        movement.y = Input.GetAxisRaw("Vertical");

        if (movement.x != 0 || movement.y != 0)
        {
            if (aniFrame1 == false)
            {
                Invoke("ChangeSprite0", 0.25f);
            }
            else
            {
                Invoke("ChangeSprite1", 0.25f);
            }
        }

    }

    void FixedUpdate()
    {

        rb.AddForce(movement * moveSpeed);
        rb.velocity = Vector2.ClampMagnitude(rb.velocity, maxSpeed);

        if (rb.velocity.magnitude < stopThreshold)
        {
            rb.velocity = new Vector2(0, 0);
        }

    }

}
